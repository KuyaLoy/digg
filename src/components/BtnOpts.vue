<template>
<b-form-group v-slot="{ ariaDescribedby }">
      <b-form-radio-group class="btnOpt"
        id="btn-radios-2"
        v-model="selected"
        :options="options"
        :aria-describedby="ariaDescribedby"
        button-variant="outline-primary"
        size="lg"
        name="hi"
        buttons
      ></b-form-radio-group>
</b-form-group>
</template>

<script>
    export default {
    data() {
      return {
        selected: 'radio1',
        options: [
          { text: 'Upto 3 months', value: '3'},
          { text: '3 to 6 months', value: '3-6'},
          { text: '6 to 12 months', value: '6-12'},
          { text: '+12 months', value: '+12'},
          { text: '+3 years', value: '+3'}
        ],
        props: {
            text: String,
        },
      }
    }
  }
</script>

<style>
.btnOpt label{
    margin-right: 10px;
    border-radius: 35px!important;
    background: #EFEFEF;
    border: none;
    color: black;
    padding: 15px 50px!important;
}

.btnOpt label:before{content: "\f00c";
    font-family: 'FontAwesome';
    margin-right: 10px;
}
.btnOpt label:hover, .btnOpt label:active{
    background: #ebeaea;
    color: black;
}

label.btn.btn-outline-primary.btn-lg.active{
    background: #cac9c9 !important;
    color: black;
    border: none !important;
}

.focus{
     box-shadow: none !important;
}

.btn-outline-primary:not(:disabled):not(.disabled):active{
    background: #cac9c9 !important;
}

</style>