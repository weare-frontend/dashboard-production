<template>
<div>
    <div class="col-4" style="margin-top: -70px; left: -65px;">
        <a href="/dashboard" class="text-white mr-4">
            <i  class="f7-icons text-white nuxt-link-active">chevron_left_circle_fill</i>
        </a>
    </div>
    
    <div class="col-12">
        <h5 class="text-center text-white font-weight-100" style="margin-top: 20px;">โปรโมชั่นทั้งหมด</h5>
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
