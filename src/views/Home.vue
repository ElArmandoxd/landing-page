<template>
  <div class="home col-lg-10 col-md-10 mx-auto container">
    <Header/>
    <br>
    <div class="social_medias row row-cols-1 row-cols-md-5 g-3 justify-content-around">
      <SocialMedia :socialMedia="s" v-for="s in social" :key="s.name"/>
    </div>
    <br>
    <div class="overview-section text-white row">
      <h2 class="col-2">Overview - Today</h2>
    </div>
    <div class="overview row row-cols-1 row-cols-md-5 g-3 justify-content-around">
      <Overview :over="o"  v-for="o in overview" :key="o.id"/>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '../components/Header.vue';
import SocialMedia from '../components/SocialMedia.vue';
import Overview from '../components/Overview.vue';

//import de iconos
import fb_icon from '../assets/icon-facebook.svg';
import is_icon from '../assets/icon-instagram.svg';
import tw_icon from '../assets/icon-twitter.svg';
import yt_icon from '../assets/icon-youtube.svg';

export default {
  name: 'Home',
  components: {
    Header,
    SocialMedia,
    Overview
  },
  data(){
    return{
      social:[
        {
          name: "Facebook",
          style: "border-radius-fb",
          tag: "@nathanf",
          followers: "1987",
          today_count: 12,
          icon: fb_icon
        },
        {
          name: "Twitter",
          style: "border-radius-tw",
          tag: "@nathanf",
          followers: "1044",
          today_count: 99,
          icon: tw_icon
        },
        {
          name: "Instagram",
          style: "border-radius-ig",
          tag: "@realnathanf",
          followers: "11k",
          today_count: 1099,
          icon: is_icon
        },
        {
          style: "border-radius-yt",
          name: "Youtube",
          tag: "Nathan F.",
          followers: "8239",
          today_count: -144,
          icon: yt_icon
        },
      ],
      overview:[
        {
          id: "1",
          icon: fb_icon,
          title: "Page Views",
          number: 87,
          percentage: 3,
        },
        {
          id: "3",
          icon: tw_icon,
          title: "Retweets",
          number: 117,
          percentage: 303,
        },
        {
          id: "2",
          icon: is_icon,
          title: "Likes",
          number: 5462,
          percentage: 2257,
        },
        {
          id: "4",
          icon: yt_icon,
          title: "Likes",
          number: 107,
          percentage: -303,
        },
        {
          id: "1",
          icon: fb_icon,
          title: "Likes",
          number: 52,
          percentage: -2,
        },
        {
          id: "3",
          icon: tw_icon,
          title: "Likes",
          number: 507,
          percentage: 553,
        },
        {
          id: "2",
          icon: is_icon,
          title: "Profile Views",
          number: "52k",
          percentage: 1375,
        },
        {
          id: "4",
          icon: yt_icon,
          title: "Total Views",
          number: 1407,
          percentage: -12,
        }
      ]
    }
  }
}
</script>