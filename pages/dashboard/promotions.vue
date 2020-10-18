<template>
  <div class="container" style=" margin-top: -10px; position: absolute; left:0; right:0;">
    <div class="row justify-content-center">
      <div class="col-8">
        <page-promotions :slides="promotionArray" />
      </div>
    </div>
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