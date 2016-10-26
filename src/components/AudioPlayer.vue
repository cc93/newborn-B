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
        width:30px;
        height:30px;
        left: 240px;
        top: 27px;
    }

    .audio-player-sound-wave1{
        left:0;
        top:5px;
    }

    .audio-player-sound-wave2{
        left:6px;
        top:3px;
    }

    .audio-player-sound-wave3{
        left:15px;
        top:0;
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
        <img src="../../img/6_s1.png" alt="" class="audio-player-speaker pa" >
        <div class="audio-player-sound-wave-box pa" v-show="isPlay">
            <img src="../../img/6_s2.png" alt="" class="audio-player-sound-wave1 pa" v-show="soundWaveFrame>=2">
            <img src="../../img/6_s3.png" alt="" class="audio-player-sound-wave2 pa" v-show="soundWaveFrame>=3">
            <img src="../../img/6_s4.png" alt="" class="audio-player-sound-wave3 pa" v-show="soundWaveFrame>=4">
        </div>
        <audio v-el:audio @canplay="canPlay=true" @play="onPlay">
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
            playingAudioVm:{
                type:Object,
                default:function () {
                    return {}
                }
            }
        },
        data: function () {
            return {
                audioEl: null,
                canPlay: false,
                currentTimeStr: '0:00',
                totalTimeStr: 0,
                progress: 0,    //[0,1]
                currentTimeUpdateIntervalId: 0,
                soundWaveFrame:1,
                soundWaveIntervalId:0
            };
        },
        watch: {
            'isPlay': function prepareToPlay(isPlay) {
                if (isPlay) {
                    if (!this.canPlay) {
                        this.audioEl.load();
                        setTimeout(()=> {
                            prepareToPlay(isPlay);
                        }, 500);
                    } else {
                        this.doPlay();
                    }
                } else {
                    this.reset();
                }
            }
        },
        ready: function () {
            this.initAudio();
        },
        methods: {
            initAudio(){
                this.audioEl = this.$els.audio;
                this.audioEl.src = this.src;
                this.audioEl.controls = false;
                this.audioEl.autoplay = false;
                this.audioEl.loop = false;
                this.audioEl.load();
                this.audioEl.oncanplay = ()=> {
                    //初始化显示时间
                    this.currentTimeStr = this.formatTime(this.audioEl.duration);
                    if (this.isPlay) {
                        this.doPlay();
                    }
                }
            },
            doPlay(){
                //停止其他音频，保证一次只能播放一个音频
                if(this.playingAudioVm){
                   this.playingAudioVm.isPlay = false 
                }
                this.audioEl.play();
                this.currentTimeUpdateIntervalId = setInterval(()=> {
                    //update current time
                    this.progress = this.audioEl.currentTime / this.audioEl.duration;
                    this.currentTimeStr = this.formatTime(this.audioEl.duration - this.audioEl.currentTime);
                }, 100);
                this.soundWaveIntervalId =  setInterval(()=>{
                    this.soundWaveFrame++;
                    if(this.soundWaveFrame>4){
                        this.soundWaveFrame =1;
                    }
                },300);
            },
            onPlay(e){
                this.$emit('on-play',this);
            },
            formatTime(second) {
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
            },
            reset(){
                clearInterval(this.currentTimeUpdateIntervalId);
                clearInterval(this.soundWaveIntervalId);
                this.audioEl.pause();
                this.audioEl.currentTime = 0;
                this.isPlay = false;
                //reset progress and time
                this.progress = 0;
                this.currentTimeStr = this.formatTime(this.audioEl.duration);
            }
        },
    }

</script>