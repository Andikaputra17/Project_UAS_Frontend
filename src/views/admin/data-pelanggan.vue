<template>
  <v-container class="mt-3">
    <v-row>
      <v-col cols="12" class="text-center">
        <span class="display-1 font-weight-bold"> Data Pelanggan </span>
      </v-col>
      <v-col cols="12">
        <v-row justify="end" align="center">
        </v-row>
      </v-col>
      <template v-for="(data, index) in productData">
        <v-col cols="12" :key="index">
          <div class="box rounded-lg py-2">
            <v-row justify="center" align="center">
              <!-- camera -->
              <v-col cols="2">
                <v-img
                  :src="data.url"
                  contain
                />
              </v-col>
              <!-- Keterangan -->
              <v-col cols="7">
                <p class="title">{{data.name}}</p>
                <p class="subtitle-1">Nama : {{data.nama}} </p>
                <p class="subtitle-1">Alamat : {{data.alamat}} </p>
                <p class="subtitle-1">Produk yang di serwa : {{data.produk_yang_di_sewa}} </p>
                <p class="subtitle-1">Id Pelanggan : {{data.id_pelanggan}} </p>
                <p class="subtitle-1">Tanggal Sewa : {{data.tanggal_sewa}} </p>
                <p class="subtitle-1">Tanggal Kembali : {{data.tanggal_kembali}} </p>
                <p class="subtitle-1">Total Transaksi : {{data.total_transaksi}} </p>
              </v-col>
              <!-- Button -->
              <v-col cols="1">
                <v-btn large block depressed dark @click="$router.push('/admin/info-pelanggan')">
                  Info
                </v-btn>
              </v-col>
              <v-col cols="1">
                <v-btn large block depressed dark>
                  Hapus
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-col>
      </template>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data: () => ({
    
    productData: [
      {
        no: "1",
        url: require("@/assets/user.png"),
        nama: "KOKO",
        alamat : "jl. hell",
        produk_yang_di_sewa : "Canon EOS R Kit 24-105mm f/4-7.1 IS STM",
        id_pelanggan : "12hd",
        tanggal_sewa : "12 agustus 2021",
        tanggal_kembali : "30 agustus 2021",
        total_transaksi : "Rp.12.000.000"
      },
           {
        no: "2",
        url: require("@/assets/user.png"),
        nama: "KOKO",
        alamat : "jl. hell",
        produk_yang_di_sewa : "Canon EOS R Kit 24-105mm f/4-7.1 IS STM",
        id_pelanggan : "12hd",
        tanggal_sewa : "12 agustus 2021",
        tanggal_kembali : "30 agustus 2021",
        total_transaksi : "Rp.12.000.000"
      },
    ],
  }),
  methods: {
    // jumpTo(val){
    //   let data = JSON.stringify(this.productData[val])
    //   let encodedData = encodeURI(data)
    //   this.$router.push({
    //     path: '/product/'+val,
    //     query: {code: encodedData}
    //   })
    // }
    jumpTo() {
      let data = this.$route.query.code;
      this.$router.push({
        path: "/Sewa",
        query: { code: data },
      });
    },
  },
};
</script>
<style>
/* .image {
  background-color: #383a39;
  cursor: pointer;
  transition: transform 0.2s;
  width: 200px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.imageBox:hover {
  transform: scale(1.1);
} */
.box{
  background-color: #C4C4C4;
}
</style>
