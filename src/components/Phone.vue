<template>
    <b-col md="1" lg="4" offset="2">
        <div class="iPhone-container" >
        <div class="ripple" v-b-tooltip.html.left="'Cick the circle <br>to continue'" v-for="item in 4" :key="item" v-bind:style="item === index ? display : null" @click="play"></div>
        <div class="iPhone-screen">
            <video preload="auto" muted="muted" autoplay="autoplay" @canplay="updatePaused" @playing="updatePaused" @pause="updatePaused" class="capture-video active-video">
            <source src="https://assets.concur.com/guided-demo/mobile/expense/vid/capture-screen_en-us.mp4" type="video/mp4" />
            </video>
        </div>
        <img class="iPhone-img" src="@/assets/image/iPhone10.png" />
        </div>
    </b-col>
</template>

<script>
  export default {
    name: 'Phone',
    data() {
      return {
        videoElement: null,
        paused: null,
        display:{
          display: 'none'
        },
        index: 0,
        timeline: [6, 14, 16, 19 ],
        progresslist: [33, 55, 75, 85, 100],
        progress: 33
      }
    },
    methods: {
      updatePaused(event) {
        this.videoElement = event.target
        this.paused = event.target.paused
      },
      play() {
        this.videoElement.play()
        if(this.index !== 4) this.track(this.timeline[this.index])
        this.progress = this.progresslist[this.index]      
        this.display = {
          display: 'none'
        }        
      },
      pause() {
        this.videoElement.pause()
        this.display = {
          display: 'block'
        }
      },
      track(time) {
        let tracker = setInterval(() => {
          console.log(this.videoElement.currentTime)
          if(this.videoElement.currentTime > time) {
            clearInterval(tracker)
            this.index++
            this.pause()
          }          
        }, 1000)
      }
    },
    mounted() {
      this.track(this.timeline[this.index])
    }
  }
</script>

<style lang="sass" scoped >  
  .tooltip
    .arrow
      &::before
        border-left-color: #fff
    .tooltip-inner
      padding: 1rem
      background-color: #fff
      color: #008fd3
  .home
    background: linear-gradient(to right, rgba(0, 0, 0, 0.9), rgba(0, 0, 0, 0.5)), url('../assets/image/dinner-bg.jpg') no-repeat
    background-size: cover
    -webkit-font-smoothing: antialiased
    position: relative
    overflow: hidden
    min-height: calc(100vh - 41px)    
    .video
      width: 2000px
      height: 100%
      position: absolute
      z-index: 0
      bottom: 0
      background: #000
      transform: translateX(-50%)
      left: 50%
    .main-container
      width: 100%
      height: 100%
      padding-top: 3vw
      .main.row
        height: 75%
        margin-bottom: 3vw               
        .iPhone-container
          width: 350px
          position: relative
          .ripple
            background-image: linear-gradient(90deg,#ffbc17,#f0ab00)
            width: 40px
            height: 40px
            border-radius: 50%
            position: absolute
            z-index: 1
            animation: ripple 1.8s infinite
            display: none
            opacity: .6
            &:first-child            
              top: 12.5%
              left: 16.5%
            &:nth-child(2)
              top: 8.5%
              left: 79.5%
            &:nth-child(3)
              top: 88%
              left: 17.5%
            &:nth-child(4)
              top: 84%
              left: 45%
            &::before
              content: ""
              position: absolute
              top: 0
              left: 0
              right: 0
              bottom: 0
              border-radius: 50%
              animation: ripple 1.8s infinite 1s
            &::after
              content: ""
              position: absolute
              top: 0
              left: 0
              right: 0
              bottom: 0
              border-radius: 50%
              animation: ripple 1.8s infinite 3s
            @keyframes ripple
                0%
                    box-shadow: 0 0 0 .7rem rgba(240, 171, 0, 0.8) 
                100%
                    box-shadow: 0 0 0 3rem rgba(240, 171, 0, 0)
          .iPhone-img
            width: 100%
          .iPhone-screen
            position: absolute
            background: #fff
            width: 284px
            height: 613px
            top: 28px
            border-radius: 33px
            right: 32px
            overflow: hidden
            video
              width: 100%
      .timeline.row
        .custom-timeline
          position: relative
          .dot-time.active
            background: #f0ab00
            color: #000
            border: none
          .dot-time
            position: absolute
            background: #333
            width: 25px
            height: 25px
            border-radius: 50%
            transform: translateY(-50%)
            color: #fff
            border: 1px solid #fff
          .second
            left: 70%
          .third
            left: 100%
          .progress-bar
            background: #f0ab00
            // &::after
            //   content: ""
            //   width: 7px
            //   height: 7px
            //   background: #f0ab00
            //   position: absolute
            //   left: 33%
            //   border-radius: 50%
</style>
