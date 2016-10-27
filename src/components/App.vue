<style>
    .bg-lightblue {
        background-color: #00aeef;
    }

    .bg-darkblue {
        background-color: #2d3446;
    }

    .app {
        width: 100%;
        height: 100%;
        position: relative;
    }

    .stage {
        width: 750px;
        height: 1334px;
        position: relative;
        overflow-y: scroll;
        overflow-x: hidden;
    }

    .page {
        width: 100%;
        height: 100%;
        position: relative;
        z-index: -10;
    }

    #page1 {
        height: 1206px;
    }

    .p1-head {
        height: 269px;
        background-color: white;
    }

    .p1-pic1-box {
        height: 434px;
        overflow: hidden;
    }

    .p1-pic1 {
        -webkit-transform: scale(1.1);
        -moz-transform: scale(1.1);
        -ms-transform: scale(1.1);
        -o-transform: scale(1.1);
        transform: scale(1.1);
    }

    .logo {
        left: 30px;
        top: 30px
    }

    .registered {
        right: 30px;
        top: 44px
    }

    .p1-timeline {
        left: 286px;
        top: 614px;
    }

    .p1-copy1 {
        left: 42px;
        top: 158px;
    }

    .p1-copy2 {
        right: 84px;
        top: 357px;
    }

    .p1-copy3 {
        left: 230px;
        top: 742px;
    }

    .p1-copy4 {
        left: 30px;
        top: 815px;
    }

    #page2 {
        height: 1165px;
    }

    .p2-head {
        height: 146px;
        background-color: white;
    }

    .p2-pic1-box {
        height: 501px;
        overflow: hidden;
    }

    .p2-timeline {
        left: 286px;
        top: 554px;
    }

    .p2-copy1 {
        left: 232px;
        top: 48px;
    }

    .p2-copy2 {
        left: 267px;
        top: 689px;
    }

    .p2-copy3 {
        left: 30px;
        top: 760px;
    }

    .p2-sponsor-arrow {
        right: 305px;
        bottom: 50px;
        font-size: 28px;
        color: #fdfd40;
    }

    .p6-sponsor-arrow {
        right: 387px;
        bottom: 50px;
        font-size: 28px;
        color: #fdfd40;
    }

    .p2-sponsor-text {
        right: 39px;
        bottom: 48px;
        font-size: 28px;
        color: #fdfd40;
        text-decoration: underline;
        font-weight: 900;
        font-family: SimHei, "Microsoft YaHei";
    }

    #page3 {
        height: 967px;
    }

    .p3-copy1 {
        left: 68px;
        top: 689px;
    }

    .p3-copy2 {
        left: 40px;
        top: 770px;
    }

    #page4 {
        height: 888px;
    }

    .p4-head {
        height: 146px;
    }

    .p4-copy1 {
        left: 145px;
        top: 165px;
    }

    .p4-copy2 {
        left: 30px;
        top: 258px
    }

    .p4-copy3 {
        left: 30px;
        top: 606px;
    }

    .p4-btn {
        left: 254px;
        bottom: 37px;
    }

    #page5 {
        height: 1050px;
    }

    .p5-head {
        height: 146px;
    }

    .p5-copy1 {
        left: 113px;
        top: 53px;
    }

    .p5-copy2 {
        left: 77px;
        top: 632px;
    }

    .p5-copy3 {
        left: 30px;
        top: 710px;
    }

    .p5-pic1 {
        left: 30px;
        top: 146px;
    }

    .p5-audio-player {
        left: 45px;
        top: 605px;
    }

    .p5-foot {
        width: 100%;
        height: 140px;
        left: 0;
        bottom: 0;
    }

    #page6 {
        height: 950px;
    }

    .p6-head {
        height: 520px;
        background-color: white;
    }

    .p6-copy1 {
        left: 218px;
        top: 53px;
    }

    .p6-copy2 {
        left: 30px;
        top: 550px;
    }

    #page7 {
        height: 1116px;
    }

    .p7-head {
        height: 146px;
        background-color: #2d3446;
    }

    .p7-pic1 {
        left: 30px;
        top: 176px;
    }

    .p7-copy2 {
        left: 112px;
        top: 600px;
    }

    .p7-copy3 {
        left: 30px;
        top: 664px;
    }

    #page8 {
        height: 1201px;
    }

    .p8-copy1 {
        left: 150px;
        top: 53px;
    }

    .p8-copy2 {
        left: 30px;
        top: 728px;
    }

    .p8-pic1 {
        left: 30px;
        top: 198px;
    }

    .p8-foot {
        width: 100%;
        height: 140px;
        left: 0;
        bottom: 0;
    }

    #page9 {
        height: 1422px;
    }

    .p9-head {
        height: 175px;
    }

    .p9-copy1 {
        left: 180px;
        top: 40px;
    }

    .p9-pic1 {
        width: 690px;
        left: 30px;
        top: 175px;
        z-index: -2;
    }

    .p9-copy2-box {
        width: 100%;
        height: 103px;
        left: 0;
        top: 838px;
    }

    .p9-copy2 {
        left: 30px;
        top: 35px;
    }

    .p9-audio-player {
        left: 45px;
        top: 968px;
    }

    .p9-copy4 {
        left: 30px;
        top: 1088px;
    }

    .p9-copy3 {
        left: 90px;
        top: 998px;
    }

    #page10 {
        height: 1400px;
    }

    .p10-copy3 {
        left: 30px;
        top: 404px;
    }

    .p10-copy4 {
        left: 30px;
        top: 488px;
    }

    .p10-copy5 {
        left: 30px;
        top: 192px;
    }

    .p10-foot {
        width: 100%;
        height: 660px;
        left: 0;
        top: 750px;
    }

    .p10-btn-box {
        left: 200px;
        top: 40px;
        width: 350px;
        height: 112px;
        border-radius: 20px;
        background-color: #fdfd40;
    }

    .p10-btn-text {
        left: 40px;
        top: 10px;
    }


</style>
<template>
    <div class="app" v-show="isLoadComplete">

        <div class="stage" v-el:stage
             v-auto-scale="{width:750}"
             @touchmove="onTouchMove"
             @scroll="computeCurrentPage">

            <div id="page1" class="page bg-lightblue">
                <div class="p1-head">
                    <img src="../../img/logo.png" alt="" class="logo pa">
                    <a :href="registeredHref">
                        <img src="../../img/registered.png" alt="" class="registered pa">
                    </a>
                    <img src="../../img/1_copy1.png" alt="" class="p1-copy1 pa">
                </div>
                <div class="p1-body">
                    <div class="p1-pic1-box">
                        <img src="../../img/1_pic1.jpg" alt="" class="p1-pic1">
                    </div>

                    <img src="../../img/1_copy2.png" alt="" class="p1-copy2 pa">
                    <timeline class="p1-timeline pa"
                              :start-time="0"
                              :end-time="20"
                              :run="currentPage==1">
                    </timeline>
                    <img src="../../img/1_copy3.png" alt="" class="p1-copy3 pa">
                    <img src="../../img/1_copy4.png" alt="" class="p1-copy4 pa">
                </div>
            </div>
            <div id="page2" class="page bg-lightblue">
                <div class="p2-head">
                    <img src="../../img/2_copy1.png" alt="" class="p2-copy1 pa">
                </div>
                <div class="p2-body">
                    <div class="p2-pic1-box">
                        <img src="../../img/2_pic1.jpg" alt="">
                    </div>
                    <timeline class="p2-timeline pa"
                              :start-time="20"
                              :end-time="40"
                              :run="currentPage==2">
                    </timeline>
                    <img src="../../img/2_copy2.png" alt="" class="p2-copy2 pa" >
                    <img src="../../img/2_copy3.png" alt="" class="p2-copy3 pa">
                    <div class="p2-sponsor-arrow pa">
                        &gt;&gt;
                    </div>
                    <a :href="sponseHref">
                        <div class="p2-sponsor-text pa">
                            支持这一分钟的改变
                        </div>
                    </a>
                </div>
            </div>
            <div id="page3" class="page bg-darkblue">
                <div class="p2-head">
                    <img src="../../img/2_copy1.png" alt="" class="p2-copy1 pa">
                </div>
                <div class="p3-body">
                    <img src="../../img/3_pic1.jpg" alt="">
                    <timeline class="p2-timeline pa"
                              :start-time="40"
                              :end-time="60"
                              :run="currentPage==3">
                    </timeline>
                    <img src="../../img/3_copy1.png" alt="" class="p3-copy1 pa">
                    <img src="../../img/3_copy2.png" alt="" class="p3-copy2 pa">
                    <div class="p2-sponsor-arrow pa">
                        &gt;&gt;
                    </div>
                    <a :href="sponseHref">
                        <div class="p2-sponsor-text pa">
                            支持这一分钟的改变
                        </div>
                    </a>
                </div>
            </div>
            <div id="page4" class="page bg-lightblue">
                <div class="p4-head">
                    <img src="../../img/logo_1.png" alt="" class="logo pa">
                </div>
                <div class="p4-body">
                    <img src="../../img/4_copy1.png" alt="" class="p4-copy1 pa">
                    <img src="../../img/4_copy2.png" alt="" class="p4-copy2 pa">
                    <img src="../../img/4_copy3.png" alt="" class="p4-copy3 pa">
                    <a :href="sponseHref">
                        <img src="../../img/4_btn.png" alt="" class="p4-btn pa">
                    </a>
                </div>
            </div>
            <div id="page5" class="page">
                <div class="p5-head">
                    <img src="../../img/6_copy1.png" alt="" class="p5-copy1 pa">
                </div>
                <div class="p5-body">
                    <img src="../../img/6_pic1.jpg" alt="" class="p5-pic1 pa">
                    <audio-player class="p5-audio-player pa" :duration="127.944"
                                  src="./audio/p5-audio.mp3" @on-play="setPlayingAudioVm" :playing-audio-vm="playingAudioVm">
                    </audio-player>
                    <img src="../../img/6_copy2.png" alt="" class="p5-copy2 pa">

                    <img src="../../img/6_copy3.png" alt="" class="p5-copy3 pa">
                </div>
                <div class="p5-foot bg-lightblue pa">
                    <a :href="sponseHref">
                        <img src="../../img/4_btn.png" alt="" class="p4-btn pa">
                    </a>
                </div>
            </div>
            <div id="page6" class="page bg-lightblue">
                <div class="p6-head">
                    <img src="../../img/7_copy1.png" alt="" class="p6-copy1 pa">
                    <img src="../../img/7_pic1.jpg" alt="" class="p5-pic1 pa">
                </div>
                <div class="p6-body">
                    <img src="../../img/7_copy2.png" alt="" class="p6-copy2 pa">
                    <div class="p6-sponsor-arrow pa">
                        &gt;&gt;
                    </div>
                    <a :href="sponseHref">
                        <div class="p2-sponsor-text pa">
                            继续支持这挽救生命的改变
                        </div>
                    </a>
                </div>
            </div>
            <div id="page7" class="page bg-lightblue">
                <div class="p7-head">
                    <img src="../../img/8_copy1.png" alt="" class="p6-copy1 pa">
                </div>
                <div class="p7-body">
                    <img src="../../img/8_pic1.jpg" alt="" class="p7-pic1 pa">
                    <img src="../../img/8_copy2.png" alt="" class="p7-copy2 pa">
                    <img src="../../img/8_copy3.png" alt="" class="p7-copy3 pa">
                    <div class="p6-sponsor-arrow pa">
                        &gt;&gt;
                    </div>
                    <a :href="sponseHref">
                        <div class="p2-sponsor-text pa">
                            继续支持这挽救生命的改变
                        </div>
                    </a>
                </div>
            </div>
            <div id="page8" class="page">
                <div class="p8-head">
                    <img src="../../img/9_copy1.png" alt="" class="p8-copy1 pa">
                </div>
                <div class="p8-body">
                    <img src="../../img/9_pic1.jpg" alt="" class="p8-pic1 pa">
                    <img src="../../img/9_copy2.png" alt="" class="p8-copy2 pa">
                </div>
                <div class="p8-foot bg-darkblue pa">
                    <a :href="sponseHref">
                        <img src="../../img/4_btn.png" alt="" class="p4-btn pa">
                    </a>
                </div>
            </div>
            <div id="page9" class="page">
                <div class="p9-head bg-lightblue">
                    <img src="../../img/10_copy1.png" alt="" class="p9-copy1 pa">
                </div>
                <div class="p9-body">
                    <img src="../../img/10_pic1.jpg" alt="" class="p9-pic1 pa">
                    <div class="p9-copy2-box bg-darkblue pa">
                        <img src="../../img/10_copy2.png" alt="" class="p9-copy2 pa">
                    </div>
                    <audio-player class="p9-audio-player pa" :duration="97.68"
                                  src="./audio/p9-audio.mp3" @on-play="setPlayingAudioVm" :playing-audio-vm="playingAudioVm">
                    </audio-player>
                    <img src="../../img/10_copy3.png" alt="" class="p9-copy3 pa">
                    <img src="../../img/10_copy4.png" alt="" class="p9-copy4 pa">
                </div>
                <div class="p8-foot bg-darkblue pa">
                    <a :href="sponseHref">
                        <img src="../../img/4_btn.png" alt="" class="p4-btn pa">
                    </a>
                </div>
            </div>
            <div id="page10" class="page bg-lightblue">
                <div class="p4-head">
                    <img src="../../img/logo_1.png" alt="" class="logo pa">
                </div>
                <div class="p4-body">
                    <img src="../../img/4_copy1.png" alt="" class="p4-copy1 pa">
                    <img src="../../img/11_copy2.png" alt="" class="p4-copy2 pa">

                    <img src="../../img/11_copy3.png" alt="" class="p10-copy3 pa">
                    <img src="../../img/11_copy4.png" alt="" class="p10-copy4 pa">
                </div>
                <div class="p10-foot bg-darkblue pa">
                    <a :href="sponseHref">
                        <div class="p10-btn-box pa">
                            <img src="../../img/11_btn-text.png" alt="" class="p10-btn-text pa">
                        </div>
                    </a>
                    <img src="../../img/11_copy5.png" alt="" class="p10-copy5 pa">
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    //        750 * 1206 设计稿
    //        采用（750 * 1334 iphone6）进行排版，缩放方式：宽度满屏
    import Timeline from './Timeline.vue'
    import AudioPlayer from  './AudioPlayer.vue'
    export default{
        components: {
            'timeline': Timeline,
            'audio-player': AudioPlayer
        },
        directives: {
            'trans': {
                update: function (val) {
                    var className = this.el.className;
                    var str = className.match(/\b([0-9A-Za-z-]+)-transition\b/g);
                    var transName = RegExp.$1;
                    var cssObj = val;
                    var ext = cssObj.ext || '%';     //默认单位是px
                    delete cssObj.ext;
                    Smart._.each(cssObj, function (v, k) {
                        Smart.Css.createSmartCssStyle('.' + transName + '-' + k, v, ext);
                    });
                }
            },
            'anim': {
                update: function (val) {
                    var name = '';
                    var time = '';
                    var timeFn = '';
                    var loop = '';
                    var ext = 'px';     //默认单位是px
                    var frames = {};    //obj, required!
                    //取得frames对象
                    if (val.frames instanceof Array) {  // val.frames is [Object Array]
                        var length = val.frames.length;
                        var lastArg = val.frames[length - 1];
                        var key = '';
                        if (typeof lastArg === 'string') {
                            ext = lastArg;
                            val.frames.splice(length - 1, 1);
                            length -= 1;
                        }
                        for (var i = 0; i < length; i++) {
                            key = (i / (length - 1) * 100).toFixed(1) + '%';
                            frames[key] = val.frames[i];
                        }
                        frames['ext'] = ext;
                    } else {     // val.frames is [Object Object]
                        frames = val.frames;
                    }
                    //取得animation的css字符串
                    if (val.animation != undefined) {
                        var str = val.animation;
                        var strArray = str.split(' ');
                        name = strArray[0];
                        time = strArray[1] || '1s';
                        timeFn = strArray[2] || 'linear';
                        loop = strArray[3] || 'infinite';
                    } else {
                        name = val.name;    // string, can be null or undefined
                        time = val.time || '1s';
                        timeFn = val.timeFn || 'linear';
                        loop = val.loop || 'infinite';
                    }
                    var anim = Smart.Animations.create(name, frames);
                    this.el.style.animation = anim.name + ' ' + time + ' ' + timeFn + ' ' + loop;
                }
            },
            'auto-scale': {
                update: function (val) {
                    var el = this.el;
                    var width = val.width;
                    var newWidth, newScale;
                    //竖屏显示
                    var resize = function () {
                        //长页面垂直滑动，宽度占满
                        newWidth = window.innerWidth;
//                        newWidth = 600;
                        newScale = newWidth / width;            //scaleX,scaleY
                        var cssSmartObj = {scale: newScale, 'transform-origin': '0 0'};
                        Smart.Css.smartCss(el, cssSmartObj, 'px');
                    }.bind(this);
                    resize();
                    console.log('newScale = ' + newScale);
                    window.onresize = function () {
                        //竖屏
                        resize();
                        console.log('newScale = ' + newScale);
                    }.bind(this);
                }
            }
        },
        data(){
            return {
                isLoadComplete: false,
                currentPage: 0,
                totalPages: 10,
                pageY: [],
                stageEl: null,
                scrollBlocked: false,
                registeredHref: 'http://www.baidu.cn/',
                sponseHref: 'http://www.unicef.cn/cn/',
                playingAudioVm:null,
                pagesHeight:[0,1206,1165,967,888,1050,950,1116,1201,1422,1133]
            }
        },
        ready(){
            this.loading();
            this.stageEl = this.$els.stage;
            var factor = 0.5;
            //factor=1/2
            //上一页的后1/2 到 这一页的前1/2  是 这一页
            //即上一页底部减上一页1/2 ， 上一页底部加上这一页的1/2 ， 上一页底部的高度就是totalY
            this.pageY = this.getPageY(factor, this.totalPages);
        },
        methods: {
            loading(){
                var Loader = Smart.Loader;
                var loader = new Loader();
                loader.addImages(document.querySelector('body'));
                //监听资源加载完成事件
                loader.addCompletionListener(function () {
                    console.log('load complete!');
                    this.isLoadComplete = true;
                    //currentPage 从0变到1 以触发第一页的动画
                    this.currentPage = 1;
                }.bind(this));
                //启动资源加载管理器
                loader.start();
            },
            getPageY(factor, totalPages){
                var totalY = 0;
                var pageY = [];
                pageY.push(0);
                for (var i = 1; i <= totalPages; i++) {
                    //factor=1/2
                    //上一页的后1/2 到 这一页的前1/2  是 这一页
                    //即上一页底部减上一页1/2 ， 上一页底部加上这一页的1/2 ， 上一页底部的高度就是totalY
                    totalY += this.pagesHeight[i];
                    pageY.push(Math.floor(totalY - this.pagesHeight[i] * factor))
                }
                return pageY;
            },
            computeCurrentPage(){
                if (!this.scrollBlocked) {
                    this.scrollBlocked = true;
                    var scrollY = this.stageEl.scrollTop;
                    //因为只有前3页Timeline用到了currentPage变量来触发，所以只要检测前3页
                    for (var i = 1; i <= 3; i++) {
                        if(scrollY>= this.pageY[i-1] && scrollY < this.pageY[i]){
                            this.currentPage = i;
                            break;
                        }
                    }
                    this.scrollBlocked = false;
                }
            },
            onTouchMove(){
                this.scrollBlocked = false;
            },
            setPlayingAudioVm(vm){
                this.playingAudioVm = vm;
            }
        }
    }

</script>
