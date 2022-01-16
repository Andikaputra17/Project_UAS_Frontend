<template>
  <v-app>
    <!-- umum -->
    <v-app-bar
      app
      color="white"
      class="px-10"
      elevate-on-scroll
      v-if="!$route.meta.admin"
    >
      <v-container>
        <v-row justify="center" align="center">
          <v-col cols="2">
            <v-img
              src="@/assets/logo.png"
              width="175px"
              height="175px"
              contain
              class="mt-1"
            />

          </v-col>
          <v-col cols="5">
            <v-text-field
              hide-details
              dense
              outlined
              label="Search"
              append-icon="mdi-magnify"
              class="rounded-xl"
            />

          </v-col>
          <v-col cols="5">
            <v-btn text height="65px" @click="$router.push('/login')">Login</v-btn>
            <v-btn text height="65px" @click="$router.push('/sign-up')">Sign Up</v-btn>
            <v-btn text height="65px" @click="$router.push('/')">Home</v-btn>
            <v-btn text height="65px" @click="$router.push('/about')">Tentang Kami</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>
    <!-- admin -->
    <v-app-bar
      app
      color="white"
      class="px-10"
      elevate-on-scroll
      v-if="$route.meta.admin"
    >
      <v-container>
        <v-row justify="center" align="center">
          <v-col cols="2">
            <v-img
              src="@/assets/logo.png"
              width="175px"
              height="175px"
              contain
              class="mt-1"
            />

          </v-col>
          <v-col cols="4">
            

          </v-col>
          <v-col cols="6">
            <v-btn text height="65px" @click="$router.push('/admin/login')">Home</v-btn>
            <v-btn text height="65px" @click="$router.push('/admin/data-camera')">Data Camera</v-btn>
            <v-btn text height="65px" @click="$router.push('/admin/data-pelanggan')">Data Pelanggan</v-btn>
            <v-btn text height="65px" @click="$router.push('/admin/logout')">Logout</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
  mounted(){
    console.log(this.$route.meta);
  }
};
</script>
<style>

</style>
