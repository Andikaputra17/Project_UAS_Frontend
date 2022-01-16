<template>
  <v-container class="mt-3">
    <v-row>
      <v-col cols="12" class="text-center">
        <span class="display-1">
          Produk
        </span>
      </v-col>
      <template v-for="(d,i) in productData">
        <v-col cols="4" :key="i">
          <div class="imageBox rounded-xl"  @click="jumpTo(i)">
            <v-img
              :src="d.url"
              class="mt-1"
            />
          </div>
          <div class="text-center mt-3">
            <span class="title">
              {{d.text}}
            </span>
          </div>
        </v-col>
      </template>
    </v-row>
  </v-container>
</template>

<script>

  export default {
    name: 'Home',
    components: {
    },
    data: () => ({
      productData: [
        {
          url: require('@/assets/canon-1.png'),
          text: 'Canon EOS R Kit 24-105mm f/4-7.1 IS STM'
        },
        {
          url: require('@/assets/nixon 1.png'),
          text: 'Nixon Z50 (Black)'
        },
        {
          url: require('@/assets/FUJI 1.png'),
          text: 'FUJIFILM X-T4 Body (Black)'
        },
        {
          url: require('@/assets/CSN31820-SONY-ZV-1_D1 1.png'),
          text: 'SONY ZV-1 Compact Camera (Black)'
        },
        {
          url: require('@/assets/Lumix.png'),
          text: 'PANASONIC Lumix DMC-GH5 II Body Mirrorless Camera'
        },
        {
          url: require('@/assets/fuji.png'),
          text: 'FUJIFILM X-T20 Double Kit XC 15-45mm + XC 50-230mm (Silver)'
        },
      ]
    }),
    methods:{
      jumpTo(val){
        let data = JSON.stringify(this.productData[val])
        let encodedData = encodeURI(data)
        this.$router.push({
          path: '/product/'+val,
          query: {code: encodedData}
        })
      }
    }
  }
</script>
<style>
.imageBox{
  background-color: #383A39;
  cursor: pointer;
  transition: transform .2s;
}
.imageBox:hover{
  transform: scale(1.1);
}
</style>
