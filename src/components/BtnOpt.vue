<template>
  <b-form-group v-slot="{ ariaDescribedby }">
      <b-form-radio-group 
        class="btnOpt"
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
        selected: null,
        options: [
          { text: 'Yes', value: 'Yes'},
          { text: 'No', value: 'No'}
        ],
        props: {
            text: String,
        },
      }
    }
  }
</script>