<template>
  <div>
    <b-form-checkbox v-model="checked1" name="check-button" class="cb_style" button>
     <i class="fas fa-heart"></i> {{ cb_title }} 
    </b-form-checkbox>
  </div>
</template>

<script>
  export default {
    props: ['cb_title'],
    data() {
      return {
        checked1: false
      }
    }
  }
</script>

<style>
.cb_style label{
    margin-right: 10px;
    border-radius: 35px!important;
    background: #EFEFEF;
    border: none;
    color: black;
    padding: 15px 50px!important;
    margin-bottom:10px!important;
}

.cb_style label:hover, .cb_style label:active{
    background: #ebeaea;
    color: black;
}

label.cb_style.active{
    background: #cac9c9 !important;
    color: black;
    border: none !important;
}

.focus{
     box-shadow: none !important;
}

</style>