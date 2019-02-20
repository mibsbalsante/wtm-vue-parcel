<template>
  <ul v-if="list.length > 0">
    <li v-for="item in list" :key="item.name">
      <div
        :style="{width: `${item.width}px`, height: `${item.height}px`, backgroundColor: item.bgColor}"
      >{{item.name}}</div>
    </li>
  </ul>
  <div v-else>Você ainda não gerou retângulos :(</div>
</template>


<script>
  export default {
    name: 'app-list',
    props: { list: Array }
  }
</script>
