<template>
  <ul class="list" v-if="list.length > 0">
    <li class="item" v-for="item in list" :key="item.name">
      <div
        :style="{width: `${item.width}px`, height: `${item.height}px`, backgroundColor: item.bgColor, border: `${item.borderWidth}px ${item.borderStyle} ${item.borderColor}`}"
      >{{item.name}}</div>
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

  .list .item {
    padding: 15px 0;
  }
</style>

