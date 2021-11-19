<template>
    <div :class="'socialMedia col '+ socialMedia.style">
        <div class="top justify-content row justify-content-center">
            <div class="icon col-1">
                <img :src="socialMedia.icon"  alt="social media icon">
            </div>
            <div class="div">
                <p class="username col-1"><strong>{{socialMedia.tag}}</strong></p>
            </div>
        </div>
        <div class="followers">
            <h1 class="numero"><strong>{{socialMedia.followers}}</strong></h1>
            <p class="follows" v-if="socialMedia.name == 'Youtube'">S U B S C R I B E R S</p>
            <p class="follows" v-else >F O L L O W E R S</p>
        </div>
        <div class="count row justify-content-center">
            <div class="arrow">
                <img :src="uparrow" alt="up_arrow" v-if="socialMedia.today_count >= 0">
                <img :src="downarrow" alt="up_arrow" v-if="socialMedia.today_count < 0">
            </div>
            <div class="news-today">
                <p v-if="socialMedia.today_count >= 0" class="positive"><strong>{{socialMedia.today_count}} Today</strong></p>
                <p v-if="socialMedia.today_count < 0" class="negative"><strong>{{socialMedia.today_count}} Today</strong> </p>
            </div>
        </div>
    </div>
</template>
<script>
import up from '../assets/icon-up.svg';
import down from '../assets/icon-down.svg';

export default {
    name: 'SocialMedia',
    props: ["socialMedia"],
    components:{
        
    },
    data(){
        return{
            uparrow: up,
            downarrow: down
        }
    },
    created(){
    },
    methods:{

    }
}
</script>

<style scoped>
.socialMedia {
    background-color: hsl(228, 28%, 20%);
    padding: 10px;
    margin-bottom: 25px;
    color: white;
    border-color: white;
    border-top:  5px solid;
    transition: transform .2s;
}
.border-radius-fb{
    border-radius: 5px !important;
    border-image-slice: 1;
    border-image-source: linear-gradient(to left, #0084ff, #0084ff);
}

.border-radius-tw{
    border-radius: 5px !important;
    border-image-slice: 1;
    border-image-source: linear-gradient(to left, #00c3ff, #00c3ff);
}

.border-radius-ig{
    border-radius: 5px !important;
    border-image-slice: 1;
    border-image-source: linear-gradient(to left, #d53a9d, #ffae00);
}

.border-radius-yt{
    border-radius: 5px !important;
    border-image-slice: 1;
    border-image-source: linear-gradient(to left, #fa1212, #ff0000);
}
.socialMedia:hover{
    transform: scale(1.025);
    background-color: hsl(230, 25%, 30%);
    cursor: pointer;
}

.username{
    color: hsl(228, 34%, 66%);
}
.follows{
    color: hsl(228, 34%, 66%)
}

.top{
    margin:15px;
}

.positive{
    color: hsl(163, 72%, 41%);
}

.negative{
    color: hsl(356, 69%, 56%);
}

h1, .h1 {
    font-size: 3.5rem;
}
</style>