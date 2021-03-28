<template>
      <b-form-radio-group class="btnOpt"
        id="btn-radios-2"
        v-model="selected"
        :options="options"
        :aria-describedby="ariaDescribedby"
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