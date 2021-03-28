<template>
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
</template>

<script>
    export default {
    data() {
      return {
        selected: 'radio1',
        options: [
          { text: 'Lifestyle', value: '3'},
          { text: 'Work Opportunities', value: 'Work Opportunities'},
          { text: 'Education', value: 'Education'},
          { text: 'Finance', value: 'Finance'},
          { text: 'Tourism', value: 'Tourism'},
          { text: 'Family', value: 'Family'},
          { text: 'Business', value: 'Business'},
          { text: 'Security', value: 'Security'},
          { text: 'The weather', value: 'The weather'},
          { text: 'Meeting new people', value: 'Meeting new people'},
          { text: 'Culture', value: 'Culture'}
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