<template>
  <v-container>
    <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">
      DỤ ÁN NỔI BẬT
    </h2>

    <v-responsive class="mx-auto mb-12" width="56">
      <v-divider class="mb-1"></v-divider>

      <v-divider></v-divider>
    </v-responsive>

    <v-carousel
      cycle
      height="600"
      hide-delimiter-background
      show-arrows-on-hover
      hide-delimiters
      :continuous="false"
    >
      <template v-for="(item, index) in articles">
        <v-carousel-item
          v-if="(index + 1) % columns === 1 || columns === 1"
          :key="index"
        >
          <v-row class="flex-nowrap">
            <template v-for="(n, i) in columns">
              <template v-if="+index + i < articles.length">
                <v-col
                  :key="i"
                  v-if="+index + i < articles.length"
                  cols="12"
                  md="4"
                >
                  <v-img
                    :src="articles[+index + i].src"
                    class="mb-4"
                    height="275"
                    max-width="100%"
                  ></v-img>

                  <h3
                    class="font-weight-black mb-4 text-uppercase"
                    v-text="articles[+index + i].title"
                  ></h3>

                  <div
                    class="title font-weight-light mb-5"
                    v-text="articles[+index + i].text"
                  ></div>

                  <v-row style="margin: 0">
                    <v-dialog v-model="dialog" width="75%">
                      <template v-slot:activator="{ on, attrs }">
                        <v-btn
                          class="ml-n4 font-weight-black"
                          text
                          v-bind="attrs"
                          v-on="on"
                          @click="
                            openPopUp(
                              articles[+index + i].id,
                              articles[+index + i].title
                            )
                          "
                        >
                          TÌM HIỂU THÊM
                        </v-btn>
                      </template>
                      <v-card>
                        <v-card-title>
                          <span class="text-h5" v-text="contentTitle"></span>
                        </v-card-title>
                        <v-card-text v-html="content"> </v-card-text>
                        <v-card-actions>
                          <v-spacer></v-spacer>
                        </v-card-actions>
                      </v-card>
                    </v-dialog>
                  </v-row>
                </v-col>
              </template>
            </template>
          </v-row>
        </v-carousel-item>
      </template>
    </v-carousel>
  </v-container>
</template>
<script>
/* eslint-disable */
import contents from "./../static/content.json";

export default {
  name: "Project",
  data: () => ({
    articles: [
      {
        id: 0,
        src: "https://kientrucdongduong.com.vn/wp-content/uploads/2020/08/thi%E1%BA%BFt-k%E1%BA%BF-c%C4%83n-h%E1%BB%99-chung-c%C6%B0-100m2.2-1024x683.jpg",
        title: "Thiết kế căn hộ chung cư 100m2 CC TIMES CITY- Anh Duy",
        text: "Với phong cách thiết kế căn hộ chung cư hiện nay. Kiến trúc đông dương đã thành công trong việc thiết kế căn hộ cho anh Duy.",
      },
      {
        id: 1,
        src: "https://kientrucdongduong.com.vn/wp-content/uploads/2020/08/pk1-1-1024x768.jpg",
        title: "Thiết kế nội thất căn hộ chung cư Matrix One C Huyền",
        text: "Kiến trúc Đông Dương sẽ cùng các bạn khám phá thế nào là thiết kế nội thất căn hộ chung cư đẹp mà chỉ có 60m2 của Matrix One Mễ trì",
      },
      {
        id: 2,
        src: "https://kientrucdongduong.com.vn/wp-content/uploads/2020/08/thiet-ke-can-ho-cao-cap-180m2.3-1024x576.jpg",
        title: "Thiết kế căn hộ cao cấp 180m2 ở CIPUTRA của anh Tài.",
        text: "Khu đô thị CIPUTRA là khu đô thị mới và cao cấp bậc nhất hiện nay. Với tổng thể bao gồm nhiều tòa nhà với những căn hộ chung cư cao cấp...",
      },
    ],
    dialog: false,
    content: "",
    contentTitle: "",
  }),
  computed: {
    columns() {
      if (this.$vuetify.breakpoint.xl) {
        return 4;
      }

      if (this.$vuetify.breakpoint.lg) {
        return 3;
      }

      if (this.$vuetify.breakpoint.md) {
        return 2;
      }

      return 1;
    },
  },
  methods: {
    openPopUp(id, title) {
      this.content = contents.find(x=>x.id === id.toString()).content;
      this.dialog = true;
      this.contentTitle = title;
    },
  },
};
</script>