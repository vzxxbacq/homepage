<template>
  <div class="resume">
    <div class="profile" ref="profile">
      <img sizes="" src="https://avatars3.githubusercontent.com/u/29952934?s=400&u=a0d6f1ab4f4a8eb77507b0552142ffb42c5ea162&v=4" alt="">
      <h2>Fang Huangqiang</h2>
      <p>Software Engineer</p>
    </div>
    <div class="span"></div>
    <div class="about">
      <h3>about me</h3>
      <p>
        Hi, I'm Living in mainland China, engaging of digital signal processing (mostly speech and music).
        I am also experienced in some NLP and CV project.
      </p>
    </div>
    <div class="contact">
      <h3>contact</h3>
      <div class="info"><i class="fas fa-building"></i> Hangzhou. ZheJiang</div>
      <a class="info" href="mailto: fhq981014@gmail.com"><i class="fas fa-envelope"></i> fhq981014@gmail.com</a>
      <div class="info"><i class="fab fa-qq"></i> 2248503552</div>
      <a class="info" href="https://vzxxbacq.cn"><i class="fab fa-internet-explorer"></i> me.vzxxbacq.cn</a>
    </div>
    <div class="media">
      <h3>Media</h3>
      <a class="media-icon"><i class="fab fa-twitter"></i></a>
      <a class="media-icon"><i class="fab fa-zhihu"></i></a>
      <a class="media-icon"><i class="fab fa-stack-overflow"></i></a>
      <a class="media-icon"><i class="fab fa-github"></i></a>
      <a class="media-icon"><i class="fab fa-weibo"></i></a>
      <a class="media-icon"><i class="fab fa-discord"></i></a>
    </div>
    <div class="exp">
      <div class="work">
        <h3>
          <i class="fa fa-briefcase icon"></i>Work Exrerience
        </h3>
        <ul>
          <li>
            <span>Software Engineer</span>
            <small>Apr 2018 - Dec 2018 (Part-time)</small>
          </li>
          <li>
            <span>Research Developer</span>
            <small>Dec 2018 - Jun 2020 (Part-time)</small>
          </li>
          <li>
            <span>Research Developer in Music</span>
            <small>Jun 2020 - now</small>
          </li>
        </ul>
      </div>
      <div class="edu">
        <h3>
          <i class="fa fa-graduation-cap icon"></i>Education
        </h3>
        <ul>
          <li>
            <span>Electrical Engineering (Bachelor)</span>
            <small>Beijing Forestry University Sept 2016 - Jun 2020</small>
          </li>
        </ul>
      </div>
    </div>
    <div class="skill">skill</div>
    <div class="pub">pub</div>
  </div>
</template>

<script>
export default {
  name: "resume",
  computed:{
    profilePos(){
      return {
        left: this.$refs['profile'].getBoundingClientRect().x,
        top: this.$refs['profile'].getBoundingClientRect().y
      };
    }
  }
}
</script>

<style scoped>
@media(max-width: 520px){
  .resume{
    display: block;
  }
  .profile::after{
    display: none;
  }
  .exp, .skill, .about{
    display: none;
  }
  .span{
    grid-area: span;
  }
}
@media(min-width: 520px) {
  a, a:visited{
    color: inherit;
  }
  .resume{
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 1fr 30px 1fr 1fr 1fr;
    grid-template-areas:
      "profile exp"
      "span skill"
      "about skill"
      "contact skill"
      "media pub";
    background: #f3f3f3;
    box-shadow: 0 2px 2px 0 rgba(0,0,0,0.14),
    0 1px 5px 0 rgba(0,0,0,0.12),
    0 3px 1px -2px rgba(0,0,0,0.2);
  }

  .span{
    grid-area: span;
  }

  .span{
    background: #8d9e78;
    height: 30px;
    margin-top: -15px;
    transform: skewY(-5deg);
  }

  .profile{
    grid-area: profile;
    background: #8d9e78;
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
    text-transform: uppercase;
    font-size: 18px;
    text-align:left;
    color: #3d405b;
  }

  .profile p{
    margin-top: 5px;
    font-size: 16px;
  }

  .profile h2, .profile p{
    letter-spacing: 0.1rem;
    text-align: center;
  }

  .profile img{
    display: block;
    margin-right: auto;
    margin-left: auto;
    border-radius: 50%;
    height: 192px;
    width: 192px;
  }

  .contact{
    margin-top: -10px;
    padding: 0 15px 0 10px;
    grid-area: contact;
    line-height: 24px;
    text-align: left;
  }

  .about{
    grid-area: about;
    padding: 30px 15px 0 10px;
  }

  .about p, .contact p{
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
    color:#e07a5f;
  }

  .info::after{
    /*background: none repeat scroll 0 0 transparent;*/
    bottom: 0;
    content: "";
    display: block;
    height: 2px;
    left: 0;
    background: #e07a5f;
    position: absolute;
    transition: width 0.3s ease 0s, left 0.3s ease 0s;
    width: 0;
  }

  .info:hover:after{
    width: 100%;
    left: 0;
  }

  .media{
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
  .media .media-icon i{
    display: inline-block;
    font-size: 30px;
    background: #8d9e78;
    width: 60px;
    height: 60px;
    color: #fcfcfc;
    border-radius: 50%;
    vertical-align: middle;
    transition-duration: 0.3s;
  }
  .media .media-icon i::before{
    display: inline-block;
    transition-duration: 0.3s;
    margin-top: 24%;
  }
  .media-icon:hover i{
    background: #e07a5f;
    border-radius: 5px;
    transform: rotate(45deg) scale(0.8);
  }
  .media-icon:hover i::before{
    display: inline-block;
    transform: rotate(-45deg) scale(1.5);
  }

  .about, .contact, .media, .exp{
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
  .work{
    grid-area: work;
  }
  .edu{
    grid-area: edu;
  }
  .skill{
    grid-area: skill;
  }
  .pub{
    grid-area: pub;
  }
  .exp, .skill, .pub{
    background: #FBFBFB;
  }
}

</style>