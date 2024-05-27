<template>
  <div>
    <svg-icon icon-class="doc" @click="click" />
  </div>
</template>

<script>
export default {
  name: 'Doc',
  methods: {
    click() {
      window.open('https://github.com/DaQinZhongGong/front-vue2-admin/', '_blank')
    }
  }
}
</script>
