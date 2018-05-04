<template>
  <div class="text">
    <textarea placeholder="按Enter发送" v-model="content" @keyup="onKeyup"></textarea>
  </div>
</template>
<script>
export default {
  name: 'sendText',
  data () {
    return {
      content: ''
    }
  },
  methods: {
    onKeyup (e) {
      if (e.keyCode === 13 && this.content.length) {
        this.$store.dispatch('sendMessage', this.content)
        this.content = ''
      }
    }
  }
}
</script>
<style lang="less" scoped>
  .text {
    height: 160px;
    border-top: solid 1px #f8f8f8;
    textarea {
      padding: 10px;
      height: 100%;
      width: 100%;
      border: none;
      outline: none;
      font-family: "Micrsofot Yahei";
      resize: none;
    }
  }
</style>
