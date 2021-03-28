<template>
  <b-form-group v-slot="{ ariaDescribedby }">
      <b-form-radio-group class="btnOpt"
        id="btn-radios-2"
        v-model="selected"
        :options="options"
        :aria-describedby="ariaDescribedby"
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