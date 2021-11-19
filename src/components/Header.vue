<template>
    <div class="title-header row align-items-center">
        <div class="title col-sm-12 col-lg-10">
            <h3 class="text">Social Media Dashboard</h3>
            <p class="text"><strong>Total Followers: 23,004</strong></p>
        </div>
        <div class="slider col-sm-12 col-lg-2 row justify-content-between">
            <p class="col-10 text"><strong>Dark Mode</strong></p>
            <div id="outer-div" class="col-2" @click="toggle">
                <div id="inner-div"></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'header',
    data(){
        return{
            toggled: false
        }
    },
    methods:{
        toggle(){
            let button = document.getElementById('inner-div');
            if(this.toggled == false){
                button.style.transition = ".4s all ease-in-out";
                button.style.transform = "translateX(21px)";
                this.toggled = true;
            }
            else{
                button.style.transition = ".4s all ease-in-out";
                button.style.transform = "translateX(0px)";
                this.toggled = false;
            }
        }
    }
}
</script>

<style scoped>
h3{
    color: white;
}

.text{
    text-align: left;
}

.title-header{
    padding-top: 30px;
}

#outer-div{
    margin: auto;
    text-align: center;
    width: 50px;
    height: 27px;
    padding: 2px;
    border-radius: 20px;
    background-color: rgb(96, 255, 96);
    background: linear-gradient(70deg, rgba(96, 255, 96,1) 0%, rgb(0, 255, 234) 100%);
    cursor: pointer;
}
#inner-div{
    width: 20px;
    height: 20px;
    border: 1px solid transparent;
    background-color: hsl(232, 19%, 15%);
    border-radius: 50px;
    position: relative;
    bottom: -2px;
}
</style>