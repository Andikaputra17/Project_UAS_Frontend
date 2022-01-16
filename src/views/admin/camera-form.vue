<template>
  <v-container class="mt-4">
    <v-row justify="center" align="center">
       <v-col cols="12" class="text-center">
        <span class="display-1 font-weight-bold"> Tambah Camera </span>
      </v-col>
      <v-col cols="5" class="formBox rounded-lg text-center pa-4">
        <v-text-field
          label="Nama Camera"
          dense
          outlined
          hide-details
        />
        <v-text-field
          label="Merk"
          dense
          outlined
          hide-details
          class="mt-4"
        />
        <v-textarea
          label="Spesifikasi"
          dense
          rows="3"
          outlined
          hide-details
          class="mt-4"
        />
        <v-text-field
          label="Harga Sewa"
          dense
          outlined
          hide-details
          class="mt-4"
        />
        <v-file-input
          label="Gambar"
          dense
          outlined
          hide-details
          class="mt-4"
        />
        <v-btn color="primary" depressed class="mt-4 rounded-xl" block @click="jumpTo()">
          Submit
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    passedData: null,
    menu: false,
    menu1: false,
    menu2: false,
    date: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
    date1: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
    time: null
  }),
  // mounted(){
  //   let decodedData = decodeURI(this.$route.query.code)
  //   let data = JSON.parse(decodedData)
  //   this.passedData = data
  // },
  //   methods:{
  //   jumpTo(){
  //     let data = this.$route.query.code
  //     this.$router.push({
  //       path: '/approved',
  //       query: {code: data}
  //     })
  //   }
  // }
}
</script>

<style>
.formBox{
  border: 1px solid black;
}
</style>