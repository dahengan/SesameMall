<template>
      <div id="toast" v-show="isShow">
          <div>{{ message }}</div>
      </div>
</template>

<script>
export default {
    name:'Toast',
    data() {
        return {
            isShow:false,
            message:''
        }
    },
    methods: {
        show(message,duration){
            this.isShow = true;
            this.message = message;
            setTimeout(()=>{
                this.isShow = false;
                this.message = '';
            },duration)
        }
    },
}
</script>

<style scoped>
#toast{
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 8px 10px;
    z-index: 999;
    color: #fff;
    background-color: rgba(0,0,0,.7);
}
</style>