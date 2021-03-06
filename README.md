# vt-button

基于 vue 2 封装出的 button 组件，提供了基本的样式和事件。

## Install

```javascript
npm i vt-button -S

import Buttons from 'vt-button'

// global install
Vue.component('Buttons', Buttons)

// scope install
export default {
    components: {
        Buttons
    }
}
```

## Usage

```example
<template>
    <Buttons @click="clickMe">click</Buttons>
    <Buttons disabled>disabled</Buttons>
    <Buttons html-type="submit" @click="submitMe">submit</Buttons>
    <Buttons size="small">small</Buttons>
    <hr />
    <Buttons type="primary">primary</Buttons>
    <Buttons type="success">success</Buttons>
    <Buttons type="loading">loading</Buttons>
    <Buttons type="warning">warning</Buttons>
    <Buttons type="info">info</Buttons>
    <Buttons type="danger">danger</Buttons>
</template>

<script>
    import Buttons from 'vt-button'

    export default {
        methods: {
            clickMe() {
                alert('点击演示')
            },
            submitMe(event) {
                alert(event.target.type)
            }
        },
        components: {
            Buttons
        }
    }
</script>
```

## Interface

```interface
props:
  type:
    type: String
    default: ''
    description: 按钮的类型，可选值: ``primary``，``success``，``loading``，``warning``，``info``，``danger``
  disabled:
    type: Boolean
    default: false
    description: 是否置灰按钮
  size:
    type: String
    default: ''
    description: 按钮的大小，可选值: ``small``，``large`` 和 ``mini``
  htmlType:
    type: String
    default: button
    description: 按钮原生的 Type 值，可选值: ``button``，``submit`` 和 ``reset``
slots:
  default:
    description: 按钮文字
events:
  click:
    description: 按钮点击事件，在移动端有 300ms 延迟
```