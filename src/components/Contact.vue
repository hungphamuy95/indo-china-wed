<template>
    <v-container>
          <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">LIÊN HỆ VỚI CHÚNG TÔI</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-theme-provider light>
            <v-row>
              <v-col cols="12">
                <v-text-field
                  flat
                  label="Tên*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-text-field
                  flat
                  label="Email*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-text-field
                  flat
                  label="Tiêu đề*"
                  solo
                ></v-text-field>
              </v-col>

              <v-col cols="12">
                <v-textarea
                  flat
                  label="Lời nhắn*"
                  solo
                ></v-textarea>
              </v-col>

              <v-col
                class="mx-auto"
                cols="auto"
              >
                <v-btn
                  color="accent"
                  x-large
                >
                  ĐĂNG KÝ
                </v-btn>
              </v-col>
            </v-row>
          </v-theme-provider>
        </v-container>
</template>

<script>

export default ({
    name: "Contact"
    
})
</script>
