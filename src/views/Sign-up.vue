<template>
  <v-container class="mt-3">
    <v-row justify="center" align="center">
      <v-col cols="5">
        <div class="py-5 rounded-lg loginBox">
          <div class="d-flex align-center">
            <v-img
              src="@/assets/logo.png"
              width="100px"
              height="100px"
              contain
            />
          </div>
            <v-container>
              <v-row justify="center" align="center">
                <v-col cols="10">
                  <v-text-field
                    outlined
                    dense
                    hide-details
                    label="Nama Lengkap"
                    class="rounded-lg"
                  />
                </v-col>
                <v-col cols="10">
                  <v-textarea
                    outlined
                    dense
                    rows="3"
                    hide-details
                    label="Alamat"
                    class="rounded-lg"
                  />
                </v-col>
                <v-col cols="10">
                  <v-text-field
                    outlined
                    dense
                    hide-details
                    label="No. Telepon"
                    class="rounded-lg"
                  />
                </v-col>
                <v-col cols="10">
                  <v-text-field
                    outlined
                    dense
                    hide-details
                    label="Email"
                    class="rounded-lg"
                  />
                </v-col>
                <v-col cols="10">
                  <v-text-field
                    outlined
                    dense
                    hide-details
                    label="Username"
                    class="rounded-lg"
                  />
                </v-col>
                <v-col cols="10">
                  <v-text-field
                    outlined
                    dense
                    hide-details
                    label="Password"
                    type="password"
                    class="rounded-lg"
                  />
                </v-col>
                <v-col cols="10" class="">
                  <v-btn block depressed class="rounded-lg" color="primary">
                    Buat akun
                  </v-btn>
                </v-col>
              </v-row>
            </v-container>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Login',

  components: {
  },
}
</script>
<style>
.loginBox{
  border: 1px solid black;
}
</style>