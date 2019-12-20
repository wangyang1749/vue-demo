<template>
  <div class="about">
    <h1>This is an about page</h1>
    <input type="text" name="" id="" v-model="model.content"><br>
    <span>{{model.content}}</span>
    <button v-on:click="show">Button</button>
  </div>
</template>
<script>
export default {
  data(){
    return{
      model:{
        content:""
      }
    }
  },
  methods:{
    
    show(){
      this.$http.get("/lovewall/1")
      .then(resp=>{
          this.model.content=resp.data.data.content
          console.log(resp.data.data)
          
      }).catch(err=>{
          console.log(err)
      })
    }
  }
}
</script>