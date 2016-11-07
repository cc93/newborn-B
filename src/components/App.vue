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

    .wrapper {
        width: 750px;
        height: 1334px;
        left:0;
        top:0;
        position: absolute;
    }

    .stage {
        width: 100%;
        height: 100%;
        left:0;
        top:0;
        position: absolute;
        overflow-y: scroll;
        overflow-x: hidden;
        opacity: 0;
    }

    .loading {
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        top: 0;
        z-index: 50;
        overflow: hidden;
        background: url(http://static.unicef.cn/201610cwh5/images/bg_0.jpg);
        background-size: cover;
        -webkit-transition: height .5s;
        transition: height .5s;
    }

    .loading-title {
        width: 100%;
        left: 0;
        top: 10%;
        z-index: 5;
    }

    .loading-cloud {
        width: 100%;
        left: 0;
        bottom: 0;
    }

    .loading-bar {
        left: 50%;
        top: 55%;
        -webkit-transform: translateX(-50%) translateY(-50%);
        transform: translateX(-50%) translateY(-50%);
    }

    .block {
        width: 100%;
        height: 100%;
        position: fixed;
        left: 0;
        top: 0;
        z-index: 99;
        overflow: hidden;
        display: none;
        background: rgba(255, 255, 255, .9);
    }

    .block-text {
        left: 50%;
        top: 50%;
        -webkit-transform: translate(-50%, 50%);
        transform: translate(-50%, 50%);
        color: #00aeef;
        font-size: 32px;
    }

    .page {
        width: 100%;
        height: 100%;
        position: relative;
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
        left: 32px;
        top: 28px;
        z-index: 2;
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
        left: 57px;
        top: 28px;
        z-index: 2;
    }

    #page10 {
        height: 1460px;
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
        height: 720px;
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
    <div class="app">
        <div class="block" :style="{display:isPortrait? 'none':'block'}">
            <p class="block-text pa">请使用竖屏浏览</p>
        </div>
        <div class="wrapper" v-auto-scale="{width:750}">
            <div class="loading" :style="{height:isLoadComplete? '0':'100%'}">
                <img class="loading-title pa" src="http://static.unicef.cn/201610cwh5/images/img_0.png" alt="">
                <img class="loading-cloud pa" src="http://static.unicef.cn/201610cwh5/images/img_1.png" alt="">
                <div id="indicatorContainer" class="loading-bar pa"></div>
            </div>
            <div class="stage"
                 :style="{opacity:isLoadComplete? 1:0}"
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
                        <img src="../../img/2_copy2.png" alt="" class="p2-copy2 pa">
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
                                      src="./audio/p5-audio.mp3" @on-play="setPlayingAudioVm"
                                      :playing-audio-vm="playingAudioVm">
                            <img src="../../img/6_copy2.png" alt="" class="p5-copy2 pa">
                        </audio-player>

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
                                      src="./audio/p9-audio.mp3" @on-play="setPlayingAudioVm"
                                      :playing-audio-vm="playingAudioVm">
                            <img src="../../img/10_copy3.png" alt="" class="p9-copy3 pa">
                        </audio-player>
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
    </div>
</template>
<script>
    import Timeline from './Timeline.vue'
    import AudioPlayer from  './AudioPlayer.vue'

    export default{
        components: {
            'timeline': Timeline,
            'audio-player': AudioPlayer,
        },
        directives: {
            'auto-scale': {
                update: function (val) {
                    var el = this.el;
                    var width = val.width;
                    var onresize = ()=> {
                        var windowSize = Smart.Utils.windowSize();
                        var winWidth = windowSize.width;
                        var winHeight = windowSize.height;
                        //缩放
                        var newScale = winWidth / width;            //scaleX,scaleY
                        var cssSmartObj = {scale: newScale, 'transform-origin': '0 0'};
                        Smart.Css.smartCss(el, cssSmartObj, 'px');
                    };
                    Smart.Event.windowEvent('resize', onresize);
                    onresize();
                }
            }
        },
        data(){
            return {
                isLoadComplete: false,
                isPortrait: true,
                currentPage: 0,
                totalPages: 10,
                pageY: [],
                scrollBlocked: false,
                registeredHref: 'http://www.baidu.cn/',
                sponseHref: 'http://www.unicef.cn/cn/',
                playingAudioVm: null,
                pagesHeight: [0, 1206, 1165, 967, 888, 1050, 950, 1116, 1201, 1422, 1133]
            }
        },
        ready(){
            this.initBlock();
            this.loading();
            var factor = 0.5;
            //factor=1/2
            //上一页的后1/2 到 这一页的前1/2  是 这一页
            //即上一页底部减上一页1/2 ， 上一页底部加上这一页的1/2 ， 上一页底部的高度就是totalY
            this.pageY = this.getPageY(factor, this.totalPages);
        },
        methods: {
            initBlock(){
                //竖屏浏览提醒
                var toggleBlock = ()=>{
                    var windowSize = Smart.Utils.windowSize();
                    if (windowSize.width < windowSize.height) {
                        this.isPortrait = true;
                    } else {
                        this.isPortrait = false;
                    }
                };
                Smart.Event.windowEvent('resize', toggleBlock);
                toggleBlock();
            },
            loading(){
                //init radialIndicator
                var radialObj = radialIndicator('#indicatorContainer', {
                    barColor: 'rgba(255,255,255,1)',
                    barBgColor: 'rgba(255,255,255,0.7)',
                    barWidth: 10,
                    initValue: 10,
                    roundCorner: true,
                    percentage: true
                });
                //init Loader
                var Loader = Smart.Loader;
                var loader = new Loader();
                loader.addImages(document.querySelector('body'));
                var startTime = new Date().getTime();
                var setLoadedPercent = (p)=> {
                    var pp = Math.ceil(Math.min((new Date().getTime() - startTime) / 25 + 10, p));
                    radialObj.animate(pp);
                    if (p >= 100) {
                        if (pp >= 100) {
                            loadedCompelte();
                        } else {
                            setTimeout(()=> {
                                setLoadedPercent(100);
                            });
                        }
                    }
                };
                var loadedCompelte = ()=> {
                    setTimeout(()=> {
                        this.isLoadComplete = true;
                        //currentPage 从0变到1 以触发第一页的动画
                        this.currentPage = 1;
                    }, 1500)
                };
                //监听资源加载进度事件
                loader.addProgressListener(function (p) {
                    setLoadedPercent(Math.max(10, p.completedCount / p.totalCount * 100));
                }.bind(this));
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
            computeCurrentPage(e){
                var scrollY = e.target.scrollTop;
                if (!this.scrollBlocked) {
                    this.scrollBlocked = true;
                    //因为只有前3页Timeline用到了currentPage变量来触发，所以只要检测前3页
                    for (var i = 1; i <= 3; i++) {
                        if (scrollY >= this.pageY[i - 1] && scrollY < this.pageY[i]) {
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
