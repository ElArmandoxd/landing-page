<template>
    <div class="overview col">
        <div class="top row justify-content-between">
            <div class="col-5">
                <p class="o_title"><strong>{{over.title}}</strong></p>
            </div>
            <div class="col-3">
                <img :src="over.icon"  alt="social media icon">
            </div>
        </div>
        <div class="bot col row justify-content-between">
            <div class="col-2">
                <h3>{{over.number}}</h3>
            </div>
            <div class="col-6 row justify-content-center">
                <div class="">
                    <img :src="uparrow" alt="up_arrow" v-if="over.percentage >= 0" >
                    <img :src="downarrow" alt="down_arrow" v-if="over.percentage < 0">
                </div>
                <div class="col-1">
                    <p v-if="over.percentage < 0 " class="negative col"><strong>{{over.percentage}}%</strong></p>
                    <p v-if="over.percentage >= 0 " class="positive col" ><strong>{{over.percentage}}%</strong></p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import up from '../assets/icon-up.svg';
import down from '../assets/icon-down.svg';


export default {
    name: 'Overview',
    props:["over"],
    components:{

    },
    data(){
        return{
            uparrow: up,
            downarrow: down
        }
    }
}
</script>

<style scoped>
.overview{
    padding: 10px;
    background-color: hsl(228, 28%, 20%);
    margin-bottom: 25px;
    margin-left: 40px;
    margin-right: 40px;
    border-radius: 5px;
    color: white;
    transition: transform .2s;
}

.overview:hover{
    transform: scale(1.025);
    background-color: hsl(230, 25%, 30%);
    cursor: pointer;
}

.o_title{
    color: hsl(228, 34%, 66%);
    text-align: left;
    margin-left: 15px;
}
.top{
    margin-bottom: 20px;
}

.positive{
    color: hsl(163, 72%, 41%);
}

.negative{
    color: hsl(356, 69%, 56%);
}

</style>