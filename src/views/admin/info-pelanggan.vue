<template>
  <v-container class="mt-3">
    <v-row justify="center" align="center">
      <v-col cols="12" class="text-center">
        <span class="display-1 font-weight-bold">Info Pelanggan</span>
      </v-col>
      <v-col cols="4">
        <v-img
          src="https://images.unsplash.com/flagged/photo-1570612861542-284f4c12e75f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cGVyc29ufGVufDB8fDB8fA%3D%3D&w=1000&q=80"
          contain
          height="350px"
          width="350px"
        />
      </v-col>
      <v-col cols="4">
        <div class="">
          <span class="subtitle-1">Nama :</span><br>
          <span class="subtitle-1">Alamat :</span><br>
          <span class="subtitle-1">No. Telp :</span><br>
          <span class="subtitle-1">Produk yang disewa :</span><br> 
          <span class="subtitle-1">Id Pelanggan :</span><br>
          <span class="subtitle-1">Tgl. Sewa :</span><br>
          <span class="subtitle-1">Tgl. Kembali :</span><br>
          <span class="subtitle-1">Total Transaksi :</span>
        </div>
        <div>
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
}
</script>

<style>

</style>