<template>
    <div class="head" @click="change">头部</div>
</template>
<script>

export default{
  data () {
    return {
    }
  },
  methods: {
    change () {
      this.bus.$emit('change', 1)
    }
  }
}

</script>
<style>
.head{
  width: 100%;
  height: 100px;
  border: 1px solid #000
}

</style>
