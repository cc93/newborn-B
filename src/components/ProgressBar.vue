<style>
    .progress-bar-container {
        position: relative;
        width: 100%;
        height: 100%;
    }

    .progress-bar-container:hover {
        cursor: pointer;
    }

    .progress-bar-total {
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 6px;
        background-color: #acc8cf;
    }

    .progress-bar-current {
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 6px;
        background-color: #00aeef;
    }

    .progress-bar-bar {
        position: absolute;
        left: 0;
        top: 0;
        width: 2px;
        height: 6px;
        margin-top: -2px;
        background-color: white;
    }

</style>
<template>
    <div class="progress-bar-container" v-el:container
         @mousedown="startDrag" @touchstart="startDrag"
         @mousemove="onDrag" @touchmove="onDrag"
         @mouseup="stopDrag" @touchend="stopDrag" @mouseleave="stopDrag">
        <div class="progress-bar-total"></div>
        <div class="progress-bar-current" :style="{transform:'scaleX('+ progress + ')','transform-origin':'0 0'}"></div>
        <div class="progress-bar-bar" v-show="barShow" :style="{left:progress*100 +'%'}"></div>
    </div>
</template>
<script>
    export default {
        props: {
            progress: {
                type: Number,
                default: 0,
                coerce: function (value) {     //[0,1]
                    return Math.min(Math.max(value,0),1);
                }
            },
            barShow: {
                type: Boolean,
                default: true
            },
            clickable: {
                type: Boolean,
                default: true
            }

        },
        data: function () {
            return {
                dragging: false,
            }
        },
        ready: function () {
            if(!this.clickable){
                this.$els.container.removeEventListener('mousedown',this.startDrag);
                this.$els.container.removeEventListener('touchstart',this.startDrag);
                this.$els.container.removeEventListener('mousemove',this.onDrag);
                this.$els.container.removeEventListener('touchmove',this.onDrag);
                this.$els.container.removeEventListener('mouseup',this.stopDrag);
                this.$els.container.removeEventListener('touchend',this.stopDrag);
                this.$els.container.removeEventListener('mouseleave',this.stopDrag);
            }
        },
        methods: {
            startDrag: function (e) {
                e = e.changedTouches ? e.changedTouches[0] : e;     //如果是触摸则取第一个触摸手指事件,如果不是触摸则取鼠标事件
                this.dragging = true;
                this.updateProgress(e);
                this.$emit('on-start-drag', e);
            },
            onDrag: function (e) {
                e = e.changedTouches ? e.changedTouches[0] : e;
                if (this.dragging) {
                    this.updateProgress(e);
                    this.$emit('on-dragging', e);
                }
            },
            stopDrag: function (e) {
                if (this.dragging) {
                    this.dragging = false;
                    this.updateProgress(e);
                    this.$emit('on-stop-drag', e);
                }
            },
            getMouseX: function (event) {
                return event.pageX || (event.clientX + (document.documentElement.scrollLeft || document.body.scrollLeft));

            },
            getMouseY: function (event) {
                return event.pageY || (event.clientY + (document.documentElement.scrollTop || document.body.scrollTop));
            },
            getContainerX: function (container) {
                var x = container.offsetLeft;
                var par = container.offsetParent;
                while (par) {
                    if (par == this.fullScreenElement()) {
                        break;
                    }
                    x += par.offsetLeft;
                    par = par.offsetParent;
                }
                return x;
            },
            getContainerY: function (container) {
                var y = container.offsetTop;
                var par = container.offsetParent;
                while (par) {
                    y += par.offsetTop;
                    par = par.offsetParent;
                }
                return y;
            },
            fullScreenElement: function () {
                return document.fullscreenElement ||
                        document.webkitFullscreenElement ||
                        document.mozFullScreenElement ||
                        document.msFullscreenElement;
            },
            updateProgress: function (event) {
                var offsetX = Math.min(this.$els.container.offsetWidth, Math.max(0, this.getMouseX(event)- this.getContainerX(this.$els.container)));   //offsetX: [0,containerWidth]
                this.progress = offsetX / this.$els.container.offsetWidth;     //progress: [0,1]
                this.$emit('on-progress-updated', this.progress);
                return true;
            }

        }
    }
</script>