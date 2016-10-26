<style>
    .timeline {
        width: 180px;
        height: 70px;
        line-height: 70px;
        text-align: center;
        font-size: 32px;
        color: #fff;
        background: url(../../img/timeline.png) no-repeat 0 0;
    }
</style>
<template>
    <div class="timeline">
        0{{Math.floor(ms10Count/6000)}}:{{Math.floor(ms10Count/1000%6)}}{{Math.floor(ms10Count/100%10)}}:{{Math.floor(ms10Count/10%10)}}{{ms10Count%10}}
    </div>
</template>
<script>
    export default{
        props: {
            run: {
                type: Boolean,
                default: false
            },
            startTime: {
                type: Number,
                default: 0
            },
            endTime: {
                type: Number,
                default: 0
            }
        },
        data(){
            return {
                ms10Count:0,
                lastTime:0
            }
        },
        watch:{
            //随时检测准备启动
            'run': function(val, oldVal){
                if(val){
                    //重置计时起点，100 *  10ms = 1s
                    this.ms10Count = this.startTime * 100;
                    this.timer();
                }
            }
        },
        ready(){
            //重置计时起点，100 *  10ms = 1s
            this.ms10Count = this.startTime * 100;
            //第一次启动
            if(this.run){
                this.timer();
            }
        },
        methods: {
            timer(){
                if(!this.run) return;
                var currentTime = new Date().getTime();
                //这里本来应该是10ms计数一次，但是JS的定时器偏慢 故要改小间隔值
                if(( currentTime - this.lastTime)> 5){
                    this.lastTime = currentTime;
                    this.ms10Count++;
                }
                //终点检测
                if(this.ms10Count >= this.endTime * 100){
                    this.$emit('time-end', this.endTime);
                    return;
                }
                setTimeout(this.timer, 0);
            }
        }
    }
</script>