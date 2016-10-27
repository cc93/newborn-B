<style>
    .audio-player {
        width: 660px;
        height: 80px;
    }

    .audio-player-blue-box {
        left: 0;
        top: 0
    }

    .audio-player-white-box {
        left: 194px;
        top: 13px;
    }

    .audio-player-speaker {
        left: 224px;
        top: 32px;
    }

    .audio-player-sound-wave-box {
        width: 30px;
        height: 30px;
        left: 240px;
        top: 27px;
    }

    .audio-player-sound-wave1 {
        left: 0;
        top: 5px;
    }

    .audio-player-sound-wave2 {
        left: 6px;
        top: 3px;
    }

    .audio-player-sound-wave3 {
        left: 15px;
        top: 0;
    }

    .audio-player-progress-bar-box {
        width: 281px;
        height: 9px;
        top: 38px;
        left: 276px;
    }

    .audio-player-current-time {
        right: 50px;
        top: 30px;
        font-size: 20px;
        color: #4b585c;
    }

</style>
<template>
    <div class="audio-player" @click="isPlay=!isPlay">
        <img src="../../img/6_line1.png" alt="" class="audio-player-blue-box pa">
        <img src="../../img/6_line2.png" alt="" class="audio-player-white-box pa">
        <img src="../../img/6_s1.png" alt="" class="audio-player-speaker pa">
        <div class="audio-player-sound-wave-box pa">
            <img src="../../img/6_s2.png" alt="" class="audio-player-sound-wave1 pa" v-show="soundWaveFrame>=2">
            <img src="../../img/6_s3.png" alt="" class="audio-player-sound-wave2 pa" v-show="soundWaveFrame>=3">
            <img src="../../img/6_s4.png" alt="" class="audio-player-sound-wave3 pa" v-show="soundWaveFrame>=4">
        </div>
        <audio v-el:audio @play="onPlay" @ended="onEnded">
            <source :src="src" type="audio/mpeg">
            Your browser does not support HTML5 audio.
        </audio>
        <div class="audio-player-progress-bar-box pa">
            <progress-bar id="audio-player-progress-bar"
                          :progress.sync="progress" :bar-show="false" :clickable="false">
            </progress-bar>
        </div>
        <div class="audio-player-current-time pa">{{currentTimeStr}}</div>
    </div>
</template>
<script>
    import ProgressBar from './ProgressBar.vue'
    export default {
        components: {'progress-bar': ProgressBar},
        props: {
            src: {
                type: String,
                default: null
            },
            isPlay: {
                type: Boolean,
                default: false
            },
            playingAudioVm: {
                type: Object,
                default: function () {
                    return {}
                }
            },
            duration: {
                type: Number,
                default: 0
            }

        },
        data: function () {
            return {
                audioEl: null,
                currentTimeStr: '0:00',
                totalTimeStr: 0,
                progress: 0,    //[0,1]
                currentTimeUpdateIntervalId: 0,
                soundWaveFrame: 100,
                soundWaveIntervalId: 0
            };
        },
        watch: {
            'isPlay': function (isPlay) {
                if (isPlay) {
                    this.doPlay();
                } else {
                    this.reset();
                }
            }
        },
        ready: function () {
            this.initAudio();
            //如果用户未设置音频时长，则自动检测
            //在iPad上自动检测时长有问题（偏短），所以推荐自己设置一个准确值
            if (!this.duration) {
                this.initDuration();
            }else {
                //自己设置了duration单位是秒，要转化成字符串显示，一开始显示的播放时间是音频总时长
                this.currentTimeStr = this.formatTime(this.duration);
            }
        },
        methods: {
            initAudio(){
                this.audioEl = this.$els.audio;
                this.audioEl.src = this.src;
                this.audioEl.controls = false;
                this.audioEl.autoplay = false;
                this.audioEl.loop = false;
            },
            initDuration(){
                setTimeout(()=> {
                    if (this.audioEl.duration) {
                        //一开始显示的播放时间是音频总时长
                        this.duration = this.audioEl.duration;
                        this.currentTimeStr = this.formatTime(this.duration);
                        //获取到了总时长就跳出此异步监测函数
                        return;
                    }
                    this.initDuration();
                }, 1000)
            },
            doPlay(){
                //停止其他音频，保证一次只能播放一个音频
                if (this.playingAudioVm && this.playingAudioVm !== this) {
                    this.playingAudioVm.isPlay = false
                }
                this.audioEl.play();
                //更新播放时间
                this.currentTimeUpdateIntervalId = setInterval(()=> {
                    //update current time
                    this.progress = this.audioEl.currentTime / this.duration;
                    //当前播放时间为倒计时
                    this.currentTimeStr = this.formatTime(this.duration - this.audioEl.currentTime);
                }, 100);
                //更新声音波纹动画帧
                this.soundWaveIntervalId = setInterval(()=> {
                    this.soundWaveFrame++;
                    if (this.soundWaveFrame > 4) {
                        this.soundWaveFrame = 1;
                    }
                }, 300);
            },
            reset(){
                //停止更新播放时间，声波动画帧
                clearInterval(this.currentTimeUpdateIntervalId);
                clearInterval(this.soundWaveIntervalId);
                //还原播放时间，声波的初始状态
                this.currentTimeStr = this.formatTime(this.duration);
                this.soundWaveFrame = 100;
                //还原进度条
                this.progress = 0;
                //还原音频
                this.audioEl.pause();
                this.audioEl.currentTime = 0;
            },
            onPlay(e){
                this.$emit('on-play', this);
            },
            onEnded(e){
                //播放结束后 需要手动标志，并重置音频
                this.isPlay = false;
                this.reset();
                this.$emit('on-end', this);
            },
            formatTime(second) {
                if (second < 0) {
                    second = 0;
                }
                var sec = 0;
                var min = 0;
                var strMin = '00', strSec = '00';
                sec = Math.floor(second % 60);
                min = Math.floor(second / 60);
                if (sec < 10) {
                    strSec = '0' + sec;
                } else {
                    strSec = sec;
                }
                strMin = min;
                return strMin + ':' + strSec;
            }
        },
    }

</script>