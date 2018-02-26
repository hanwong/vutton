<template>
  <div class="vutton">
    <svg :width="width" :height="height" xmlns="http://www.w3.org/2000/svg">
      <rect class="vutton__border" :width="width" :height="height" />
    </svg>
    <div class="vutton__text">hover it!</div>
  </div>
</template>

<script>
export default {
  name: 'Vutton',
  props: {
    width: { default: 200 },
    height: { default: 60 },
    strokeWidth: { default: 5 },
    strokeDash: { default: 200 },
    strokeColorDefault: { default: '#42b983' },
    strokeColorAni: { default: '#42b983' },
    duration: { default: 1 }
  },
  mounted () {
    let vuttonAni
    let dashOffset = (this.width*2 + this.height*2)

    let vutton = document.querySelector('.vutton') 
    vutton.style.width = `${this.width}px`
    vutton.style.height = `${this.height}px`

    let aniStyles = document.styleSheets
    Array.from(aniStyles).forEach( style => {
      Array.from(style.cssRules).forEach( rule => {
        if (rule.name === 'vutton__ani') {
          rule.cssRules[0].style.strokeDasharray = `${this.strokeDash} ${this.width*2}`
          rule.cssRules[0].style.strokeDashoffset = 0
          rule.cssRules[0].style.strokeWidth = `${this.strokeWidth}px`
          rule.cssRules[0].style.stroke = this.strokeColorAni

          rule.cssRules[1].style.strokeDasharray = `${this.strokeDash} ${dashOffset - this.strokeDash}`
          rule.cssRules[1].style.strokeDashoffset = -dashOffset
          rule.cssRules[1].style.strokeWidth = `${this.strokeWidth}px`
          rule.cssRules[1].style.stroke = this.strokeColorAni
        }

        if (rule.selectorText === '.vutton:hover .vutton__border') {
          rule.style.animationDuration = `${this.duration}s`
        }
      })
    })

    let borderStyles = document.querySelector('.vutton__border')
    borderStyles.style.strokeDasharray = dashOffset
    borderStyles.style.strokeWidth = this.strokeWidth
    borderStyles.style.stroke = this.strokeColorDefault
    
    let textStyles = document.querySelector('.vutton__text')
    textStyles.style.lineHeight = `${this.height}px`
    

  }
}
</script>

<style>
.vutton {
  position: relative;
  width: 200px;
  height: 60px;
  cursor: pointer;
}

.vutton__border {
  fill: transparent;
  stroke-dasharray: 520;
  stroke-dashoffset: 0;
  stroke-width: 4px;
  stroke: #42b983;
}

.vutton__text {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100%;
  transform: translate(-50%, -50%);
  text-align: center;
  color: #34495e;
  line-height: 60px;
}

@keyframes vutton__ani {
  0% {
    stroke-dasharray: 200 400;
    stroke-dashoffset: 0;
    stroke-width: 4px;
    stroke: #42b983;
  }
  100% {
    stroke-dasharray: 200 320;
    stroke-dashoffset: -520;
    stroke-width: 4px;
    stroke: #42b983;
  }
}

.vutton:hover .vutton__border {
  -webkit-animation: 3s vutton__ani linear forwards infinite;
  animation: 3s vutton__ani linear forwards infinite;
}
</style>
