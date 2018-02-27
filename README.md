<p align="center">
  <img src="example/vutton-demo/src/assets/vutton.svg"/>
</p>
<p align="center">
  <video src="example/vutton-demo/src/assets/vutton.mov" autoplay></video>
</p>

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




