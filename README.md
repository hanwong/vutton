<style>
.vutton {
  position: relative;
  margin: 0 auto;
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
  font-size: 1rem;
  letter-spacing: 0.2rem;
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

<br><br><br>
<p align="center">
  <img src="https://hanwong.github.io/vutton/example/vutton-demo/src/assets/vutton.svg"/>
</p>
<br><br><br>
<!-- <p align="center">
  <img style="width: 50%" src="https://hanwong.github.io/vutton/example/vutton-demo/src/assets/vutton.gif">
</p> -->


<div class="vutton">
  <svg width="200" height="60" xmlns="http://www.w3.org/2000/svg">
    <rect class="vutton__border" width="200" height="60" />
  </svg>
  <div class="vutton__text">
    hover it!
  </div>
</div>

<br><br><br>


> Vuejs SVG Animation Button

### Install
```npm
npm install --save vutton
```

### Usage
```js
import Vutton from 'vutton'

export default {
  components: {
    Vutton
  }
}
```

```html
 <Vutton 
  :width="300" 
  :height="80"
  :strokeWidth="5"
  :strokeDash="250"
  strokeColorDefault="#42b983"
  strokeColorAni="#51e0a0"
  :duration="2"
  >
  <div>hover it!</div>
</Vutton>
```

### Attribute

| Props | Description | Type | Default |
|-----------|-------------|------|---------|
| width | button width | Number | 200 (px) |
| height | button height | Number | 60 (px) |
| strokeWidth | border line thick | Number | 5 |
| strokeDash | border length | Number | 200 |
| strokeColorDefault | default status color | String | #42b983 |
| strokeColorAni | hover status color | String | #42b983 |
| duration | 1 time animation duration | Number | 1 (s) |


### Slot

| Name | Description |
|-----------|-------------|
| - | text content of button |




<!---->
