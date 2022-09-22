<template>
  <div class="dictionary">
    <div class="col-12 d-flex justify-center dictionary__control-block control-block">
      <v-btn
        class="control-block__button mt-16 d-flex"
        width="350"
        height="40"
        @click="dialog = !dialog"
      >
        <v-icon>mdi-plus</v-icon>
        Add new word
      </v-btn>
    </div>
    <div class="dictionary__list"></div>

    <v-dialog
      v-model="dialog"
      max-width="500px"
    >
      <v-card>
        <v-card-text class="d-flex pt-5 pb-0">
          <v-text-field class="col-6" v-model="dialogWord" label="Your word"></v-text-field>
          <v-text-field class="col-6" v-model="dialogWordTranslate" label="Word's translate"></v-text-field>
        </v-card-text>

        <v-card-actions class="pb-4">
          <v-spacer></v-spacer>

          <v-btn
            text
            color="primary"
            @click="addWord"
          >
            Add word
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
export default {
  name: 'dictionary',
  data() {
    return {
      dialog: false,
      dialogWord: '',
      dialogWordTranslate: '',
      wordsList: [
        {
          name: 'abandoned',
          translate: 'заброшенный',
        },
        {
          name: 'evolve',
          translate: 'развиваться',
        },
        {
          name: 'involve',
          translate: 'вовлекать',
        },
        {
          name: 'sage',
          translate: 'мудрец',
        }
      ],
    }
  },
  methods: {
    addWord(data) {
      this.dialog = false
      this.wordsList.unshift(data)
    },
  },
}
</script>

<style scoped>

</style>
