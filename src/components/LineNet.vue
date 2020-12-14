<template>
    <b-col md="1" lg="4" offset="2" class="content-container" >
        <img 
        class="marker"
        v-bind:style="{ opacity: 0, animationName: 'marker', animationDelay: '5s' }"
        src="@/assets/image/pin_orange.svg"
        />
        <div class="h-lines">
        <div 
            v-for="(item, index) in 9" 
            :key="index"
            v-bind:style="{ top: item*10 + '%'  }"
            class="line-item"
        ></div>
        </div>
        <div class="v-lines">
        <div 
            v-for="(item, index) in 9" 
            :key="index"
            v-bind:style="{ left: item*10 + '%'  }"
            class="line-item"
        ></div>
        </div>
        <div class="dots">
        <div 
            class="dot"
            v-bind:style="{ top: 'calc(20% - 4px)', left: 'calc(20% - 4px)' }"
        ></div>
        <div 
            class="dot"
            v-bind:style="{ top: 'calc(20% - 4px)', left: 'calc(50% - 4px)' }"
        ></div>
        <div 
            class="dot"
            v-bind:style="{ top: 'calc(70% - 4px)', left: 'calc(50% - 4px)' }"
        ></div>
        <div 
            class="dot"
            v-bind:style="{ top: 'calc(70% - 4px)', left: 'calc(70% - 4px)' }"
        ></div>
        <div 
            class="dot"
            v-bind:style="{ top: 'calc(50% - 4px)', left: 'calc(70% - 4px)' }"
        ></div>
        <div 
            class="dot"
            v-bind:style="{ top: 'calc(50% - 4px)', left: 'calc(90% - 4px)' }"
        ></div>
        </div>
        <div class="v-dot-lines">
        <div 
            class="dot-line"
            v-bind:style="{ top: '20%', left: '20%', width: '0%', animationName: 'width30', animationDelay: '0s' }"
        ></div>
            <div 
            class="dot-line"
            v-bind:style="{ top: '70%', left: '50%', width: '0%', animationName: 'width20', animationDelay: '2s' }"
        ></div>
            <div 
            class="dot-line"
            v-bind:style="{ top: '50%', left: '70%', width: '0%', animationName: 'width20', animationDelay: '4s' }"
        ></div>
        </div>
        <div class="h-dot-lines">
        <div 
            class="dot-line"
            v-bind:style="{ top: '20%', left: '50%', height: '0%', animationName: 'height50', animationDelay: '1s' }"
        ></div>
            <div 
            class="dot-line reverse"
            v-bind:style="{ top: '70%', left: '70%', height: '0%', animationName: 'height20', animationDelay: '3s' }"
        ></div>
        </div>
        <div class="content">
        <div>
            <h5>You take an Uber to get to the conference.</h5>
            <p>The extensive system of SAP Concur supplier and App Center integrations means receipts from services such as Uber for Business are automatically recognized.</p>
        </div>
        </div>
    </b-col>
</template>

<script>
  export default {
    name: 'LineNet'
  }
</script>

<style lang="sass"> 
.content-container
    min-height: 50vh
    min-width: 30vw
    .marker
        width: 44px
        position: absolute
        right: calc(10% - 22px)
        display: flex
        justify-content: center
        align-items: center
        font-size: 3rem
        top: calc(50% - 68px)
        pointer-events: all
        animation-fill-mode: forwards
        animation-duration: 1s
        cursor: pointer
    .line-item
        opacity: .5
        position: absolute
        transform: matrix(1, 0, 0, 1, 0, 0)
    .dot-line
        position: absolute
        background: #008fd3
        animation-fill-mode: forwards
        animation-duration: 1s
    @keyframes width20
        0%
            width: 0            
        100%
            width: 20%
    @keyframes width30
        0%
            width: 0            
        100%
            width: 30%
    @keyframes height50
        0%
            height: 0            
        100%
            height: 50%
    @keyframes height20
        0%
            height: 0
            top: 70%         
        100%
            height: 20%
            top: 50%
    @keyframes marker
        0%
            opacity: 0
        100%
            opacity: 1
    .h-lines .line-item
        background: linear-gradient(90deg,transparent,hsla(0,0%,88.2%,.3),hsla(0,0%,88.2%,.3),hsla(0,0%,88.2%,.3),transparent)
        height: 1px
        width: 100%
    .v-lines .line-item
        background: linear-gradient(0deg,transparent,hsla(0,0%,88.2%,.3),hsla(0,0%,88.2%,.3),hsla(0,0%,88.2%,.3),transparent)
        width: 1px
        height: 100%
    .dots .dot
        position: absolute
        width: 8px
        height: 8px
        background: #d4d4d4
        border-radius: 50%
        z-index: 1
    .v-dot-lines .dot-line
        height: 1px
    .h-dot-lines .dot-line
        width: 1px
    .content
        height: 100%
        display: flex
        align-items: center
        width: 80%
        text-align: left 
</style>
