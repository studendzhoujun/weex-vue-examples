<template>
  <scroller class="wrapper">
    <div class="header" @click="openURL('https://www.w3.org/TR/css-flexbox-1/#flex-shrink-property')">
      <text class="title">flex-shrink</text>
    </div>
    <div class="example-panel">
      <text class="tips">A:_ B:_ C:_ D:_</text>
      <div class="container border row">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">A:_ B:1 C:_ D:_</text>
      <div class="container border row">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B" style="flex-shrink:1"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">A:_ B:99 C:_ D:_</text>
      <div class="container border row">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B" style="flex-shrink:99"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">A:_ B:1 C:_ D:1</text>
      <div class="container border row">
        <div class="box A"><text class="label">A</text></div>
        <div class="box B" style="flex-shrink:1"><text class="label">B</text></div>
        <div class="box C"><text class="label">C</text></div>
        <div class="box D" style="flex-shrink:1"><text class="label">D</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">A:1 B:1 C:1 D:1</text>
      <div class="container border row">
        <div class="box A" style="flex-shrink:1"><text class="label">A</text></div>
        <div class="box B" style="flex-shrink:1"><text class="label">B</text></div>
        <div class="box C" style="flex-shrink:1"><text class="label">C</text></div>
        <div class="box D" style="flex-shrink:1"><text class="label">D</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">A:2 B:1 C:2 D:_</text>
      <div class="container border row">
        <div class="box A" style="flex-shrink:2"><text class="label">A</text></div>
        <div class="box B" style="flex-shrink:1"><text class="label">B</text></div>
        <div class="box C" style="flex-shrink:2"><text class="label">C</text></div>
        <div class="box D"><text class="label">D</text></div>
      </div>
    </div>
    <div class="example-panel">
      <text class="tips">A:8 B:4 C:2 D:1</text>
      <div class="container border row">
        <div class="box A" style="flex-shrink:8"><text class="label">A</text></div>
        <div class="box B" style="flex-shrink:4"><text class="label">B</text></div>
        <div class="box C" style="flex-shrink:2"><text class="label">C</text></div>
        <div class="box D" style="flex-shrink:1"><text class="label">D</text></div>
      </div>
    </div>
  </scroller>
</template>

<style scoped>
  .header {
    height: 120px;
    background-color: #00B4FF;
    justify-content: center;
    margin-bottom: 60px;
  }
  .title {
    font-size: 50px;
    text-align: center;
    color: #ffffff;
    font-family: monospace;
  }
  .row {
    flex-direction: row;
  }
  .example-panel {
    align-items: center;
    justify-content: center;
    margin-bottom: 50px;
  }
  .tips {
    font-size: 30px;
    color: #888888;
    padding-bottom: 10px;
    font-family: monospace;
  }
  .border {
    border-width: 2px;
    border-style: solid;
    border-color: #888888;
  }
  .container {
    width: 600px;
    height: 160px;
  }
  .vertical-container {
    width: 300px;
    height: 450px;
  }
  .box {
    height: 100px;
    justify-content: center;
    align-items: center;
  }
  .A { background-color: #ff7070; }
  .B { background-color: #66b966; }
  .C { background-color: #519fff; }
  .D { background-color: #ffb37d; }
  .label {
    width: 180px;
    text-align: center;
    font-size: 66px;
    color: #FFF;
  }
</style>

<script>
  const navigator = weex.requireModule('navigator')
  const storage = weex.requireModule('storage')
  export default {
    methods: {
      openURL (url) {
        const hash = 'ab57ab447248c35115144736ba38521a'
        const link = WXEnvironment.platform === 'Web'
          ? `http://dotwe.org/raw/htmlVue/${hash}`
          : `http://dotwe.org/raw/dist/${hash}.bundle.wx`
        storage.setItem('CURRENT_DOCUMENT_URL', url)
        navigator.push({ url: `${link}?_wx_tpl=${link}` })
      }
    }
  }
</script>
