<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      height="100"
    >
      <v-avatar
        class="mr-3"
        color="grey lighten-5"
        size="70"
      >
        <v-img
          contain
          max-height="70%"
          src="https://2.pik.vn/2021b5e7402f-3ea5-4cae-a6ec-732258f2f7f0.jpg"
        ></v-img>
      </v-avatar>

      <v-toolbar-title class="font-weight-black headline">
        INDOCHINA ARCHITECT
      </v-toolbar-title>
    </v-app-bar>

    <v-content>
      <section id="hero">
        <v-row no-gutters>
          <v-img
            :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
            src="https://b-f10-zpcloud.zdn.vn/2509029069971990422/70fff169da8a09d4509b.jpg"
          >
            <v-theme-provider dark>
              <v-container fill-height>
                <v-row
                  align="center"
                  class="white--text mx-auto"
                  justify="center"
                >
                  <v-col
                    class="white--text text-center"
                    cols="12"
                    tag="h1"
                  >
                    <span
                    :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
                      class="font-weight-light"
                    >
                      <span class="titlespan">Chào mừng tới</span>
                    </span>

                    <br>

                    <span
                      :class="[$vuetify.breakpoint.smAndDown ? 'display-2': 'display-3']"
                      class="font-weight-black"
                    >
                      <span class="titlespan">KIẾN TRÚC ĐÔNG ĐƯƠNG</span>
                    </span>

                  </v-col>

                  <v-btn
                    class="align-self-end"
                    fab
                    outlined
                    @click="$vuetify.goTo('#about-me')"
                  >
                    <v-icon>mdi-chevron-double-down</v-icon>
                  </v-btn>
                </v-row>
              </v-container>
            </v-theme-provider>
          </v-img>
        </v-row>
      </section>

      <section id="about-me">
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">Về Công ty</h2>

          <v-responsive
            class="mx-auto mb-8"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            Kiến trúc Đông Dương là công ty tư vấn thiết kế hàng đầu Việt Nam trong lĩnh vực xây dựng công trình dân dụng
          </v-responsive>

          <div></div>

        </v-container>

        <div class="py-12"></div>
      </section>

      <section
        id="features"
        class="grey lighten-3"
      >
        <div class="py-12"></div>

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">DỊCH VỤ CỦA CHÚNG TÔI</h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1"></v-divider>

            <v-divider></v-divider>
          </v-responsive>

          <v-row>
            <v-col
              v-for="({ icon, title, text }, i) in features"
              :key="i"
              cols="12"
              md="4"
            >
              <v-card
                class="py-12 px-4"
                color="grey lighten-5"
                flat
              >
                <v-theme-provider dark>
                  <div>
                    <v-avatar
                      color="primary"
                      size="88"
                    >
                      <v-icon
                        large
                        v-text="icon"
                      ></v-icon>
                    </v-avatar>
                  </div>
                </v-theme-provider>

                <v-card-title
                  class="justify-center font-weight-black text-uppercase"
                  v-text="title"
                ></v-card-title>

                <v-card-text
                  class="subtitle-1"
                  v-text="text"
                >
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>

        <div class="py-12"></div>
      </section>

      <section id="stats">
        <v-parallax
          :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
          src="https://images.unsplash.com/photo-1510915228340-29c85a43dcfe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80"
        >
          <v-container fill-height>
            <v-row class="mx-auto">
              <v-col
                v-for="[value, title] of stats"
                :key="title"
                cols="12"
                md="3"
              >
                <div class="text-center">
                  <div
                    class="display-3 font-weight-black mb-4"
                    v-text="value"
                  ></div>

                  <div
                    class="title font-weight-regular text-uppercase"
                    v-text="title"
                  ></div>
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-parallax>
      </section>

      <section id="blog">
        <div class="py-12"></div>

        <project></project>

        <div class="py-12"></div>
      </section>

      <v-sheet
        id="contact"
        color="#333333"
        dark
        tag="section"
        tile
      >
        <div class="py-12"></div>

        <contact></contact>

        <div class="py-12"></div>
      </v-sheet>
    </v-content>
    <v-fab-transition>
      <v-btn
        fixed
        fab
        large
        dark
        bottom
        left
        class="v-btn--example"
        href="tel:0918273645"
        color="error"
      >
        <v-icon>mdi-phone</v-icon>
      </v-btn>
    </v-fab-transition>
    <v-footer
      class="justify-center"
      color="#292929"
      height="100"
    >
      <div class="title font-weight-light grey--text text--lighten-1 text-center">
        &copy; {{ (new Date()).getFullYear() }} — Kiến Trúc Đông Dương
      </div>
    </v-footer>
  </v-app>
</template>

<script>
import Contact from './components/Contact.vue';
import Project from './components/Project.vue'
export default {
  name: 'App',

  components: {
    Contact: Contact,
    Project: Project
  },

  data: () => ({
        features: [
          {
            icon: 'mdi-hammer-wrench',
            title: 'Thiết kế nội thất, kiến trúc',
            text: 'Thiết kế 3D không gian nội thất, bổ kỹ thuật bản vẽ sản xuất, lựa chọn các loại vật liệu đưa ra sự tư vấn phù hợp và tốt nhất cho từng đối tượng khách hàng.',
          },
          {
            icon: 'mdi-wall',
            title: 'Thi công công trình',
            text: 'Lập kế hoạch tổ chức thi công hoàn thiện, sản xuất theo bản vẽ thiết kế, lắp đặt bàn giao cho chủ đầu tư. Quản lý dự án kiến trúc, xây dựng, nội thất.',
          },
          {
            icon: 'mdi-hand-saw',
            title: 'Sản xuất đồ gỗ nội thất',
            text: 'Với đội ngũ nghệ nhân lành nghề, chúng tôi đã và đang tạo ra những sản phẩm nội thất cực kì chất lượng và được đánh giá rất cao trên thị trường Việt Nam.',
          },
        ],
        stats: [
          ['1230', 'DỰ ÁN ĐÃ THIẾT KẾ'],
          ['330+', 'DỰ ÁN ĐÃ THI CÔNG'],
          ['800', 'KHÁCH HÀNG ĐƯỢC PHỤC VỤ'],
          ['120', 'NHÂN VIÊN VÀ KIẾN TRÚC SƯ'],
        ],
  }),
};
</script>
<style scoped>
.titlespan {
  color: white;
  text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000,
    1px 1px 0 #000;
}
</style>