<template>
  <div>
    <br>
    <h6 class="subtitle" style="text-align: center;">โปรโมชั่นทั้งหมด</h6>
    <client-only placeholder="Loading...">
      <carousel-3d :display="3" :perspective="0" :space="300" :autoplay='true' :autoplay-timeout='2400' :width="300" :height="300" class="width" >
        <slide v-for="(pro, i) in slides" :index="i" :key="i">
          <figure>
            <img :src="pro.img" />
          </figure>
        </slide>
      </carousel-3d>
    </client-only>
  </div>
</template>

<script>
 
export default {
  props: {
    slides: Array,
  },
}
</script>