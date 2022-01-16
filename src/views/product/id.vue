<template>
  <v-container class="mt-3">
    <v-row justify="center" align="center" no-gutters>
      <v-col cols="12" class="text-center">
        <span class="display-1">Deskripsi Produk</span>
      </v-col>
      <v-col cols="6">
        <v-img
          :src="passedData.url"
          class="mt-1"
          height="500px"
          width="500px"
        />
      </v-col>
      <v-col cols="4">
        <div>
          <p class="display-1">{{passedData.text}}</p>
        </div>
        <div>
          <p class="subtitle-1">30.3MP Full-Frame CMOS Sensor.
          DIGIC 8 Image Processor.
          UHD 4K30 Video; C-Log & 10-Bit HDMI Out.
          Dual Pixel CMOS AF, 5655 AF Points.
          3.69m-Dot OLED Electronic Viewfinder.
          3.15″ 2.1m-Dot Swivel Touchscreen LCD.
          Expanded ISO 50-102400, 8 fps Shooting.
          Multi-Function Bar, Dual Pixel RAW.
         </p>
         <p class="subtitle-1 red--text">Harga Sewa : Rp. 400.000 (1 Hari)</p>
        </div>
        <div>
          <v-row>
            <v-col cols="4">
              <v-text-field
                type="number"
                label="Qty"
                outlined
                dense
                hide-details
                class="rounded-xl"
                v-model="qty"
              />

            </v-col>
            <v-col cols="4">
              <v-btn class="rounded-xl" depressed color="primary" @click="jumpTo()">
                Sewa Sekarang
              </v-btn>

            </v-col>
          </v-row>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Product',
  data: () => ({
    passedData: null,
    qty: 1
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
        path: '/sewa',
        query: {code: data}
      })
    }
  }
}
</script>

<style>

</style>