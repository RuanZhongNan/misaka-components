<template>
  <div class="hello">
    <button :class="'i-button-size-'+size" :disabled="disabled">
      <slot></slot>
    </button>
  </div>
</template>

<script>
function oneOf(value, arr){
  if(arr.includes(value)){
    return true;
  }else{
    return false;
  }
}
export default {
  name: 'iButton',
  props: {
    size:{
      validator(value){
          return oneOf(value, ['small', 'large', 'default']);
      },
      default:'default'
    },
    disabled:{
      type:Boolean,
      default: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
i-button-size-large{
  height: 100px;
  width:200px;
}
</style>
