<template>
  <v-container class="mt-3">
    <v-row>
      <v-img
              src="@/assets/approved 1.png"
              width="336px"
              height="356px"
              contain
            />
        <v-col cols="12" class="text-center">
        <span class="display-1"><br>
          Booking Berhasil
        </span>
        <!-- <p>Untuk Proses Selanjutatnya, klik tautan Dibawah ini</p> -->
        <p><br> Klik <a href="https://wa.me/6287753182025">disini</a> Untuk info lebih lengkap</p>
        </v-col>
            <v-col cols="12" align="center" justify="center">
              <v-btn class="rounded-xl" depressed color="primary" @click="jumpTo()">
                Cetak Bukti Booking
              </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
