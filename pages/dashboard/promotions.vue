<template>
  <div class="container" style="max-width: 540px; margin-top: -10px;position: absolute;">
    <page-promotions :slides="promotionArray" />
  </div>
</template>



<script>
import Promotions from "~/components/Promotions.vue";
export default {
  head() {
    return {
      title: "Promotions",
    };
  },
  asyncData: async function ({ $axios, env }) {
    const promotion = await $axios.$get(
      "/api/get-promotion/get-all-path-photo"
    );
    let promotionArray = promotion.data.map((item) => {
      item.img = env.API + item.img;
      return item;
    });
    return { promotionArray: promotionArray };
  },
  components: {
    "page-promotions": Promotions,
  },
  computed: {
    getSettingObject: function () {
      return this.$store.getters.getSettingObject;
    },
  },
  mounted: function () {
    console.log(this.promotionArray);
  },
};
</script>