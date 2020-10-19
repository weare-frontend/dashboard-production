<template>
<div>
    <div class="col-4" style="margin-top: -160px; left: -65px;">
         <nuxt-link :to="{name:'dashboard'}">
            <i  class="f7-icons text-white nuxt-link-active">chevron_left_circle_fill</i>
        </nuxt-link>
    </div>
    
    <div class="col-12">
        <h5 class="text-center text-white font-weight-100" style="margin-top: 110px;">โปรโมชั่นทั้งหมด</h5>
    </div>
    <br>
    <br>
    <client-only placeholder="Loading...">
        <carousel-3d :display="3" :perspective="0" :space="300" :autoplay='true' :autoplay-timeout='2400' :width="300" :height="300" class="width">
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
