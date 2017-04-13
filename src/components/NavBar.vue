<template>

  <Menu :class="{ 'mainnav' : true,'nav-top': !scrolled }" v-scroll="onScroll" mode="horizontal" :style="style" active-name="1">
    <div class="warp">

    <div class="items">
        <Menu-item name="1">
            首页
        </Menu-item>
        <Menu-item name="2">
            业务联系
        </Menu-item>
        <Menu-item name="3">
            在线支持
        </Menu-item>

    </div>
    </div>
    </Menu>

</template>

<script>
export default {
  data () {
    return {
      'scrolled': true,
      'scrollY': 0
    }
  },
  methods: {
    onScroll: function (scrollY) {
      console.log(scrollY)
      if (scrollY > 0 !== this.scrolled) {
        this.scrolled = scrollY > 0
      }
    }
  },
  watch: {
  },
  computed: {
    style () {
      return {
        'background': this.scrolled ? 'white' : 'transparent'
      }
    }
  },
  directives: {
    scroll: {
      bind: function (el, binding) {
        window.addEventListener('scroll', () => {
          binding.value(document.body.scrollTop)
        })
      }
    }
  }
}
</script>

<style scoped>
.items{
    float: right;
}
.mainnav{
    width:100%;
    z-index:1000;
    position:fixed;
}
.nav-top{
    
}
.nav-top:after{
    background: transparent !important;
}
</style>
