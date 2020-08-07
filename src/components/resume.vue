<template>
  <div class="resume">
    <div class="my-profile" ref="my-profile">
      <img sizes="" src="https://avatars3.githubusercontent.com/u/29952934?s=400&u=a0d6f1ab4f4a8eb77507b0552142ffb42c5ea162&v=4" alt="">
      <h2>Fang Huangqiang</h2>
      <p>Software Engineer</p>
    </div>
    <div class="my-span"></div>
    <div class="about">
      <h3>about me</h3>
      <p>
        Hi, I'm living in HangZhou, working on digital signal processing (mostly speech and music).
        I am also experienced in some NLP and CV project. 
      </p>
    </div>
    <div class="my-contact">
      <h3>contact</h3>
      <div class="info"><i class="fas fa-building"></i> Hangzhou. ZheJiang</div>
      <a class="info" href="mailto: fhq981014@gmail.com"><i class="fas fa-envelope"></i> fhq981014@gmail.com</a>
      <div class="info"><i class="fab fa-qq"></i> 2248503552</div>
      <a class="info" href="https://vzxxbacq.cn"><i class="fab fa-internet-explorer"></i> www.vzxxbacq.cn</a>
    </div>
    <div class="my-media">
      <h3>Media</h3>
      <a class="media-icon"><i class="fab fa-twitter"></i></a>
      <a class="media-icon"><i class="fab fa-zhihu"></i></a>
      <a class="media-icon"><i class="fab fa-stack-overflow"></i></a>
      <a class="media-icon"><i class="fab fa-github"></i></a>
      <a class="media-icon"><i class="fab fa-weibo"></i></a>
      <a class="media-icon"><i class="fab fa-discord"></i></a>
    </div>
    <div class="right">
      <div class="exp">
        <div class="work">
          <h3>
            <i class="fa fa-briefcase icon"></i>Work Exrerience
          </h3>
          <ul>
            <li>
              <span>Software Engineer</span>
              <small>Institute of Computing, CAS<br>Apr 2018 - Dec 2018 (Part-time)</small>
            </li>
            <li>
              <span>Research Developer</span>
              <small>IBM China<br>Dec 2018 - Jul 2019 (Part-time)</small>
            </li>
            <li>
              <span>Research Developer</span>
              <small>Tianyin Entertainment Inc.<br>Jun 2020 - now</small>
            </li>
          </ul>
        </div>
        <div class="edu">
          <h3>
            <i class="fa fa-graduation-cap icon"></i>Education
          </h3>
          <ul>
            <li>
              <span>Electrical Engineering </span>
              <small>Beijing Forestry University<br> Sept 2016 - Jun 2020</small>
            </li>
          </ul>
        </div>
      </div>
      <div class="skill">
        <h3><i class="fas fa-code"></i>Programming Skill</h3>
        <ul>
          <li v-for="(data, index) in pSkill" :key="index">
            <span>{{ data.name }}</span>

            <div class="empty-bar">
              <div class="bar" :style="{width: data.value + '%', transitionDuration: 0.5 + 's'}"></div>
            </div>
          </li>
        </ul>
      </div>
      <div class="proj">
        <h3><i class="fas fa-cog"></i>Project</h3>
        <ul>
          <li class="repo" v-for="(repo, index) in repos" :key="index">
            <RepoCard :repo="repo" :pad="71" style="height: 50%"/>
          </li>
        </ul>
      </div>
      <div class="pub">
        <h3><i class="fas fa-paperclip"></i>Publication</h3>
        <ul>
          <li v-for="(p, i) in pub" :key="i">{{ p }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import RepoCard from './RepoCard'
export default {
  name: "resume",
  components: {RepoCard},
  mounted() {
    setTimeout(function (){

    }, 100)
  },
  data(){
    return {
      pSkill: [
          { name: "Speech Process", value: 95},
          {name: "C++ & Python", value: 80},
          {name: "LinuxDevOps", value: 70},
          {name: "Java & Javascript", value: 60},
          {name: "FrontEnd", value: 50},
          {name: "BackEnd", value: 50},
      ],
      repos: [
          'vzxxbacq/speaker-recognition-papers',
          'vzxxbacq/repo-card-vue'
      ],
      pub: [
          "H. Fang, Y. He, W. Xu, Y. Xu, D. Ke and K. Su, \"A Generalized Denoising Method with an Optimized Loss Function for Automated Bird Sound Recognition,\" ICCCS, Shanghai, China, 2020, pp."
      ]
    }
  },
  computed:{
  }
}
</script>

<style scoped>
*, *::before, *::after{
  box-sizing: revert!important;
}
@media(max-width: 520px){

}
@media(min-width: 0px) {
  .proj ul{
    margin-left: -15px;
    padding: 0;
    list-style-type: none;
  }
  .repo{
    display: inline-block;
    width: 47.5%;
    padding: 0 10px 0 0;
  }
  .empty-bar{
    display: inline-block;
    background: #cdcdcd;
    height: 2px;
    margin-bottom: 5px;
    width: calc(100% - 160px);
    position: relative;
    border-radius: 2px;
  }
  .pub ul {
    list-style-type: none;
    text-align: left;
    padding: 5px;
  }
  .skill ul li{
    margin: 8px;
    text-align: left;
  }
  .skill ul li span{
    display: inline-block;
    argin: 2px;
    width: 120px;
  }
  .bar{
    position: absolute;
    display: inline-block;
    margin-bottom: 4px;
    height: 4px;
    top: -1px;
    background: #24292e;
    box-shadow: 0 0 0 #24292e;
    border-radius: 5px;
    width: 200px;
  }
  small:before{
    content: "\A";
    white-space: pre;
  }
  a, a:visited{
    color: inherit;
  }
  .resume{
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 1fr 30px 1fr 1fr 1fr;
    grid-template-areas:
      "my-profile right"
      "span right"
      "about right"
      "my-contact right"
      "media right";
    background: #f3f3f3;
    box-shadow: 0 2px 2px 0 rgba(0,0,0,0.14),
    0 1px 5px 0 rgba(0,0,0,0.12),
    0 3px 1px -2px rgba(0,0,0,0.2);
  }

  .my-span{
    grid-area: span;
    background: #24292e;
    height: 30px;
    margin-top: -15px;
    transform: skewY(-5deg);
  }


  .my-profile{
    grid-area: my-profile;
    background: #24292e;
    color: #fbfbfb;
    padding: 30px 15px 5px 15px;
    z-index: 2;
    margin-bottom: 0;
    font-size: 1.5em;
    font-weight: normal;
    text-align: left;
  }

  h2{
    margin-top: 30px;
    margin-bottom: 0;
    font-size: 18px;
  }

  h3{
    padding: 18px 0 18px 0;
    font-weight: bold;
    text-transform: uppercase;
    font-size: 18px;
    text-align:left;
    color: #3d405b;
  }

  .my-profile p{
    margin-top: 5px;
    font-size: 16px;
  }

  .my-profile h2, .my-profile p{
    letter-spacing: 0.1rem;
    text-align: center;
  }

  .my-profile img{
    display: block;
    margin-right: auto;
    margin-left: auto;
    border-radius: 50%;
    height: 192px;
    width: 192px;
  }

  .my-contact{
    margin-top: -10px;
    padding: 0 15px 0 10px;
    grid-area: my-contact;
    line-height: 24px;
    text-align: left;
  }

  .about{
    grid-area: about;
    padding: 30px 15px 0 10px;
  }

  .about p, .my-contact p{
    padding: 10px;
  }

  .info{
    display: inline-block;
    margin: 5px auto 10px auto;
    position: relative;
    text-decoration: none;
    transition: 0.3s;
  }

  .info:hover{
    color:#0366d6;
  }

  .info::after{
    /*background: none repeat scroll 0 0 transparent;*/
    bottom: 0;
    content: "";
    display: block;
    height: 2px;
    left: 0;
    background: #0366d6;
    position: absolute;
    transition: width 0.3s ease 0s, left 0.3s ease 0s;
    width: 0;
  }

  .info:hover:after{
    width: 100%;
    left: 0;
  }

  .my-media{
    grid-area: media;
    margin-top: -40px;
    padding: 0 15px 5px 10px;
  }
  .media-icon{
    display: inline-block;
    text-align: center;
    vertical-align: middle;
    margin: 7px 25px 7px 25px;
  }
  .my-media .media-icon i{
    display: inline-block;
    font-size: 30px;
    background: #24292e;
    width: 60px;
    height: 60px;
    color: #fcfcfc;
    border-radius: 50%;
    vertical-align: middle;
    transition-duration: 0.3s;
  }
  .my-media .media-icon i::before{
    display: inline-block;
    transition-duration: 0.3s;
    margin-top: 24%;
  }
  .media-icon:hover i{
    background: #0366d6;
    border-radius: 5px;
    transform: rotate(45deg) scale(0.8);
  }
  .media-icon:hover i::before{
    display: inline-block;
    transform: rotate(-45deg) scale(1.5);
  }

  .about, .my-contact, .my-media, .exp{
    z-index: 2;
    margin-bottom: 0;
    font-size: 17px;
    letter-spacing: 0.3px;
    font-weight: normal;
    text-align: left;
  }

  .exp{
    grid-area: exp;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-areas: "work edu";
    padding: 10px 0 0 20px;
  }

  .work:hover h3, .edu:hover h3,
  .skill:hover h3, .pub:hover h3,
  .proj:hover h3{
    letter-spacing: 0.1rem;
    transition-duration: 0.3s;
  }

  .work:hover h3 i, .edu:hover h3 i,
  .skill:hover h3 i, .pub:hover h3 i, .proj:hover h3 i{
    transition-duration: 0.3s;
    transform: scale(1.1);
  }

  .exp h3 i, .skill h3 i, .pub h3 i, .proj h3 i {
    background: #24292e;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    color: #fbfbfb;
    text-align: center;
    margin-right: 5px;
  }

  .exp h3 i:before, .skill h3 i:before, .pub h3 i:before,
  .proj h3 i:before{
    display: block;
    margin-top: 10px;
  }
  .work{
    grid-area: work;
  }
  .edu{
    grid-area: edu;
  }

  .work ul, .edu ul, .skill ul{
    list-style-type: none;
    padding: 0;
  }
  .work li, .edu li{
    position: relative;
    margin-left: 15px;
    padding-left: 15px;
    padding-bottom: 15px;
  }
  .work li:first-of-type:before, .edu li:first-of-type:before{
    width: 10px;
    height: 10px;
    left: -2px;
  }
  .work li:before, .edu li:before{
    content: "";
    width: 7px;
    height: 7px;
    border: 3px solid #3d405b;
    background: #fcfcfc;
    border-radius: 50%;
    left: 0;
    z-index: 1;
    position: absolute;
    display: block;
  }

  .work li:after, .edu li:after{
    position: absolute;
    display: block;
    content: "";
    width: 3px;
    height: 100%;
    background: #3d405b;
    left: 5px;
    top: 0;
  }

  li:hover:before{
    animation: circle 1.2s infinite;
  }

  li:hover span{
    color: #0366d6;
  }

  li:hover .bar{
    background: #0366d6;
    box-shadow: 0 0 0 1px #0366d6;
  }

  @keyframes circle {
    from{
      box-shadow: 0 0 0 0 rgba(61, 64, 91, 1);
    }
    to{
      box-shadow: 0 0 0 6px rgba(61, 64, 91, 0);
    }
  }

  .skill{
    grid-area: skill;
    z-index: 3;
    padding: 0 0 0 20px;
  }

  .pub{
    grid-area: pub;
    z-index: 4;
    margin-top: 0;
    padding: 0 0 0 20px;
  }

  .proj{
    grid-area: project;
    padding: 0 0 0 20px;
  }

  .exp, .skill, .pub, .proj{
    background: #fbfbfb;
  }

  .right{
    grid-area: right;
    background: #fbfbfb;
    grid-template-rows: 1fr 50px 1fr 1fr 1fr;
    grid-template-areas:
        "exp"
        "skill"
        "skill"
        "project"
        "pub";
    display: grid;
  }
  .right:hover > div:not(:hover) {
    opacity: 0.6;
    transition: 0.5s;
    background: #fbfbfb;
  }
}
</style>