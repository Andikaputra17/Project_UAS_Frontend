<template>
  <v-container class="mt-3">
    <v-row>
      <v-col cols="12" class="text-center">
        <span class="display-1 font-weight-bold"> Data Camera </span>
      </v-col>
      <v-col cols="12">
        <v-row justify="end" align="center">
          <v-col cols="1">
            <v-btn depressed outlined @click="$router.push('/admin/camera-form')">
              <v-icon>
                mdi-plus
              </v-icon>
            </v-btn>
          </v-col>
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
                <p class="subtitle-1">Status : {{data.status}} </p>
              </v-col>
              <!-- Button -->
              <v-col cols="1">
                <v-btn large block depressed dark @click="$router.push('/admin/edit-camera')">
                  Edit
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
        url: require("@/assets/canon-1.png"),
        Status: "disewakan",
        name: "Canon EOS R Kit 24-105mm f/4-7.1 IS STM"
      },
      {
        no: "2",
        url: require("@/assets/nixon 1.png"),
        Status: "tersedia",
        name: "Canon EOS R Kit 24-105mm f/4-7.1 IS STM"
      },
      {
        no: "3",
        url: require("@/assets/FUJI 1.png"),
        Status: "disewakan",
        name: "Canon EOS R Kit 24-105mm f/4-7.1 IS STM"
      },
      {
        no: "4",
        url: require("@/assets/CSN31820-SONY-ZV-1_D1 1.png"),
        Status: "disewakan",
        name: "Canon EOS R Kit 24-105mm f/4-7.1 IS STM"
      },
      {
        no: "5",
        url: require("@/assets/Lumix.png"),
        Status: "tersedia",
        name: "Canon EOS R Kit 24-105mm f/4-7.1 IS STM"
      },
      {
        no: "6",
        url: require("@/assets/fuji.png"),
        Status: "disewakan",
        name: "Canon EOS R Kit 24-105mm f/4-7.1 IS STM"
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
