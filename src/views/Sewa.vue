<template>
  <v-container class="mt-4">
    <v-row justify="center" align="center">
      <v-col cols="6">
        <span class="headline">{{passedData.text}}</span>
        <v-img
          :src="passedData.url"
          height="500px"
          width="500px"
        />
      </v-col>
      <v-col cols="5" class="formBox rounded-lg text-center pa-4">
        <span class="title mt-4">Data Diri</span>
        <v-text-field
          label="Nama Lengkap"
          dense
          outlined
          hide-details
          class="mt-4"
        />
        <v-textarea
          label="Alamat"
          dense
          rows="3"
          outlined
          hide-details
          class="mt-4"
        />
        <v-text-field
          label="No. Telepon"
          dense
          outlined
          hide-details
          class="mt-4"
        />
        <v-file-input
          label="Foto KTP"
          dense
          outlined
          hide-details
          class="mt-4"
        />
        <v-row class="mt-4" no-gutters>
          <v-col cols="12" class="text-start pb-2">
            <span class="subtitle-1">Tanggal peminjaman :</span>
          </v-col>
          <v-col cols="6">
            <v-menu
              v-model="menu"
              :close-on-content-click="false"
              :nudge-right="40"
              transition="scale-transition"
              offset-y
              min-width="auto"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-text-field
                  v-model="date"
                  label="Dari"
                  prepend-icon="mdi-calendar"
                  readonly
                  dense
                  outlined
                  hide-details
                  v-bind="attrs"
                  v-on="on"
                ></v-text-field>
              </template>
              <v-date-picker
                v-model="date"
                @input="menu = false"
              ></v-date-picker>
            </v-menu>
          </v-col>
          <v-col cols="6">
            <v-menu
              v-model="menu1"
              :close-on-content-click="false"
              :nudge-right="40"
              transition="scale-transition"
              offset-y
              min-width="auto"
            >
              <template v-slot:activator="{ on, attrs }">
                <v-text-field
                  v-model="date1"
                  label="Sampai"
                  prepend-icon="mdi-calendar"
                  readonly
                  dense
                  outlined
                  hide-details
                  v-bind="attrs"
                  v-on="on"
                ></v-text-field>
              </template>
              <v-date-picker
                v-model="date"
                @input="menu1 = false"
              ></v-date-picker>
            </v-menu>
          </v-col>
        </v-row>
        <v-menu
          ref="menu"
          v-model="menu2"
          :close-on-content-click="false"
          :nudge-right="40"
          :return-value.sync="time"
          transition="scale-transition"
          offset-y
          max-width="290px"
          min-width="290px"
        >
          <template v-slot:activator="{ on, attrs }">
            <v-text-field
              v-model="time"
              label="Waktu Pengembalian"
              prepend-icon="mdi-clock-time-four-outline"
              class="mt-4"
              readonly
              dense
              outlined
              hide-details
              v-bind="attrs"
              v-on="on"
            ></v-text-field>
          </template>
          <v-time-picker
            v-if="menu2"
            v-model="time"
            full-width
            format="24hr"
            @click:minute="$refs.menu.save(time)"
          ></v-time-picker>
        </v-menu>
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
  mounted(){
    let decodedData = decodeURI(this.$route.query.code)
    let data = JSON.parse(decodedData)
    this.passedData = data
  },
    methods:{
    jumpTo(){
      let data = this.$route.query.code
      this.$router.push({
        path: '/approved',
        query: {code: data}
      })
    }
  }
}
</script>

<style>
.formBox{
  border: 1px solid black;
}
</style>
