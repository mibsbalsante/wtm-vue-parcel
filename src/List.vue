<template>
  <ul class="list" v-if="list.length > 0">
    <li class="item" v-for="item in list" :key="item.name">
      <h2 class="title">{{item.name}}</h2>
      <div
        :style="{width: `${item.width}px`, height: `${item.height}px`, backgroundColor: item.bgColor, border: `${item.borderWidth}px ${item.borderStyle} ${item.borderColor}`}"
      ></div>
      <pre class="pre">{
        <code class="code">      width: {{item.width}}px,
        height: {{item.height}}px,
        background-color: {{item.bgColor}},
        border: {{item.borderWidth}}px {{item.borderStyle}} {{item.borderColor}}</code>
      }</pre>
    </li>
  </ul>
  <p class="empty" v-else>Você ainda não gerou retângulos :(</p>
</template>


<script>
  export default {
    name: 'app-list',
    props: { list: Array }
  }
</script>

<style scoped>
  .empty {
    text-align: center;
    font-size: 20px;
  }

  .list {
    list-style: none;
    padding: 0;
  }

  .item {
    padding: 15px 0;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }

  .title {
    width: 100%;
  }

  .pre {
    white-space: pre-line;
    margin: 0;
    background-color: #eee;
    padding: 5px;
    height: 100%;
  }

  .code {
    white-space: pre-wrap;
  }
</style>

