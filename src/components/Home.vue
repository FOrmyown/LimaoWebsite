<template>
  <div class="home">
    <div class="kbimg">
        <div class="warp">
         <div class="text">
          <p>狸猫软件工作室</p>
          <p class="typing-text">{{ preText + editingText }}</p>
         </div>
        </div>
    </div>
    
    
    <div class="block">
    <div class="warp">
       <Row type="flex" justify="space-between" class="code-row-bg">
        <Col span="6">
          <Card class="card" :bordered="false">
                <h3>网站开发</h3>
                <p>快速构建传统的桌面应用程序快速构建传统的桌面应用程序快速构建传统的桌面应用程序</p>
            </Card>
        </Col>
        <Col span="6">
            <Card class="card" :bordered="false">
                <h3>APP开发</h3>
                <p>快速构建传统的桌面应用程序快速构建传统的桌面应用程序快速构建传统的桌面应用程序</p>
            </Card>
        </Col>
        <Col span="6">
            <Card class="card" :bordered="false">
                <h3>桌面软件开发</h3>
                <p>快速构建传统的桌面应用程序快速构建传统的桌面应用程序快速构建传统的桌面应用程序</p>
            </Card>
        </Col>
        <Col span="6">
            <Card class="card" :bordered="false">
                <h3>专业技术解答</h3>
                <p>快速构建传统的桌面应用程序快速构建传统的桌面应用程序快速构建传统的桌面应用程序</p>
            </Card>
        </Col>
    </Row>
    </div>
    </div>
    <div class="split-bar">
    
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      preText: '我们是: ',
      text: '专业 快速 安全的软件提供商',
      editingText: '',
      index: -1,
      intervalId: 0
    }
  },
  methods: {
    updateEditing () {
      this.index ++
      if (this.index === this.text.length) {
        this.index = -1
        this.editingText = ''
        return
      }
      this.editingText += this.text[this.index]
    }
  },
  mounted () {
    this.intervalId = window.setInterval(this.updateEditing, 300)
  },
  beforeDestroy () {
    window.clearInterval(this.intervalId)
  }
}
</script>


<style scoped>
.home{
  position:relative;
}
.carousel{
  height: 350px;
  overflow: hidden;
}
.main-content{
  height:200px;
  
}
.text{
  padding-top: 200px;
  padding-left: 40px;
  //text-align:center;
  color: white;
}
.text p{
  font-size:35px;
}

.kbimg{
  height: 900px;
  min-height: 100vh;
  padding: 60px 0;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center top;   
  background-image: linear-gradient(rgba(0, 10, 20, 0.5) 40%, rgb(8, 8, 24)), url(https://brave.com/assets/img/bg/brave-notebook_sml.jpg);
}
.typing-text{
  padding-top: 30px;
}
.typing-text:after{
  content: "";
  width: 5px;
  height: 40px;
  vertical-align: -8px;
  margin-left: 5px;
  background-color: #fff;
  display: inline-block;
  animation: blink 1s infinite alternate;
}
@keyframes blink {
    0%, 100% {
    }
    50% {
        background-color: transparent;
    }
}
.split-bar{
  height:0px;

}
.split-bar:after{
  content: "";
  display: inline-block;
    width: 0;
    height: 0;
    border-style: solid;
    border-width: 25px 0 25px 90vw;
    border-color: transparent transparent transparent rgb(255, 80, 0);
    -webkit-transform: translate3d(0, -25px, 0);
    -moz-transform: translate3d(0, -25px, 0);
    -ms-transform: translate3d(0, -25px, 0);
    -o-transform: translate3d(0, -25px, 0);
    transform: translate3d(0, -25px, 0);
}
.block{
  padding-top: 100px;
  padding-bottom: 100px;
  background:rgb(245,245,245);
}
.card{
  height:280px;
  text-align:left;
  background: transparent;
}
.cardr:hover{
  content: "";
  width: 100%;
  height: 30px;
}
.card h3{
  padding-bottom:14px;
}
</style>
