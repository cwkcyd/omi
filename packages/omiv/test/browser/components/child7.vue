<template>
  <div id="app">
    <span class="count">{{ $state.count }}</span>
    <button @click="$store.add">Increment</button>
  </div>
</template>

<script>
export default {
  store: new (class {
    data = {
      count: 2
    }
    sub = () => {
      this.data.count--
    }
    add = () => {
      this.data.count++
    }
  })(),
  use: ['count']
}
</script>
