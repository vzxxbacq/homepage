<template>
  <div class="resume">
    <div class="base">
      <div class="profile">
        <div class="photo">
          <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/764024/profile/profile-512.jpg" />
        </div>
        <div class="info">
          <h4 class="name">Kelly Chen</h4>
          <small class="job">Research Developer in Music and Speech</small>
        </div>
      </div>
      <div class="about">
        <h3>About me</h3>嗨！目前正努力學習中，希望自己的進步及成長能夠被看見，請多指教。
        <br />喜歡塗鴉、動漫和美好的小事物，歡迎交流 v(´∀｀*v)
      </div>
      <div class="contact">
        <h3>Contact</h3>
        <div class="call">
          <div class="fa fa-phone icon"></div>
          <span>(+886)900-000-000</span>
        </div>
        <div class="address">
          <div class="fa fa-map-marker icon"></div>
          <span>Taipei, Taiwan</span>
        </div>
        <div class="email">
          <div class="fa fa-envelope icon"></div>
          <span>ヽ(*´∀`)@gmail.com</span>
        </div>
        <div class="website">
          <a href="http://codepen.io/xichen" target="_blank">
            <div class="fa fa-home icon"></div>
            <span>codepen.io/xichen</span>
          </a>
        </div>
      </div>
      <div class="follow">
        <h3>Follow</h3>
        <div class="box">
          <a href="javascript:void(0);">
            <div class="icon">
              <div class="fab fa-facebook-f norotate"></div>
            </div>
          </a>
          <a href="javascript:void(0);">
			<div class="icon">
              <div class="fab fa-weibo norotate"></div>
			</div>
          </a>
          <a href="javascript:void(0);">
            <div class="icon">
              <div class="fab fa-twitter norotate"></div>
            </div>
          </a>
          <a href="javascript:void(0);">
            <div class="icon">
              <div class="fab fa-pinterest-p norotate"></div>
            </div>
          </a>
          <a href="javascript:void(0);">
            <div class="icon">
              <div class="fab fa-tumblr norotate"></div>
            </div>
          </a>
          <a href="https://codepen.io/xichen/" target="_blank">
            <div class="icon">
              <div class="fab fa-codepen norotate"></div>
            </div></a>
        </div>
      </div>
    </div>
    <div class="func">
      <div class="work">
        <h3>
          <div class="fa fa-briefcase icon"></div>Work Exrerience
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
          <div class="fa fa-graduation-cap icon"></div>Education
        </h3>
        <ul>
          <li>
            <span>Electrical Engineering (Bachelor)</span>
            <small>Beijing Forestry University Sept 2016 - Jun 2020</small>
          </li>
        </ul>
      </div>
      <div class="skills-prog">
        <h3>
          <div class="fa fa-code icon"></div>Programming Skills
        </h3>
        <ul>
          <li v-for="(key, item) in programSkills" :key=item>
            <span> {{ item }} </span>
            <div class="skills-bar">
              <div class="bar" :style="{'width': key + '%', 'transition': 0.3+'s'}"></div>
            </div>
          </li>
        </ul>
      </div>
      <div class="skills-soft"> 
        <h3>
          <div class="fa fa-th-list icon"></div>Software Skills
        </h3>
        <ul>
          <li v-for="(key, item) in softSkills" :key=item>
            <svg viewBox="0 0 100 100">
              <circle :cx="cir.height" :cy="cir.width" :r="cir.radius" />
              <circle class="cbar" cx="50" cy="50" r="45" :style="{'stroke-dashoffset': getCirclePX(key) + 'px', 'stroke-dasharray': cir.radius*3.1415926*2+'px', 'transition': 0.6+'s' }"/>
            </svg>
            <span>{{ item }}</span>
            <small>{{ key }}%</small>
          </li>
        </ul>
      </div>
      <div class="interests">
        <h3>
          <div class="fa fa-star icon"></div>Interests
        </h3>
        <div class="interests-items">
          <div class="embedded"><i class="icon fas fa-microchip "></i><span>Tech Related</span></div>
          <div class="movie"><i class="fa fa-film icon"></i><span>Movie</span></div>
          <div class="music"><i class="fa fa-headphones icon"></i><span>Music</span></div>
          <div class="game"><i class="fa fa-gamepad icon"></i><span>Game</span></div>
        </div>        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return {
      cir: {
        height: 50,
        width: 50,
        radius: 45
      },
      softSkills: {
        "Matlab": 0,
        "SolidWorks": 0,
        "AutoCAD": 0,
      },
      programSkills: {
        "Speech Processing": 0,
        "DSP": 0,
        "Linux Ops": 0,
        "Backend Dev": 0,
        "Frontend Dev": 0,
      }
    }
  },
  methods: {
    getCirclePX(value) {
      return (100 - value) / 100 * (this.cir.radius*3.1415926*2 - 0.01)
    },
    init() {
      let cir_data = [50, 50, 45]
      for(let i = 0; i < Object.keys(this.cir).length; i++){
        let k = Object.keys(this.cir)[i]
        this.cir[k] = cir_data[i];
      }

      let vm = this;

      let pskill = [95, 90, 88, 60, 50]
      for(let i = 0; i < Object.keys(this.programSkills).length; i++){
        setTimeout(function (){
          let k = Object.keys(vm.programSkills)[i]
          vm.programSkills[k] = pskill[i];
        }, i*150)
      }

      let sskill = [80.0, 60.0, 50.0]
      for(let i = 0; i < Object.keys(this.softSkills).length; i++){
        setTimeout(function (){
          let k = Object.keys(vm.softSkills)[i]
          vm.softSkills[k] = sskill[i];
        }, i * 150)
      }

    }
  },
  mounted(){
    setTimeout(this.init, 1)
  }
};
</script>

<style scoped>
* {
  outline: none;
}

h3{
  letter-spacing: 1.2px;
}

body,
html {
  margin: 0;
  background: #eee;
  font-family: "Helvetica", "Microsoft Yahei", "sans-serif";
  letter-spacing: 0.65px;
  font-size: 15px;
  color: #555;
  cursor: default;
}

a {
  text-decoration: none;
  color: #555;
  display: block;
  transition-duration: 0.3s;
}

ul {
  list-style-type: none;
  padding: 0;
}

h3 {
  color: #3d405b;
  margin: 10px 0;
  text-transform: uppercase;
  font-size: 18px;
}

.resume {
  width: 870px;
  background: #fbfbfb;
  margin: 20px auto;
  border: 1px solid #bbb;
  box-shadow: 0 0 20px -3px #bbb;
  position: relative;
  display: flex;
}

.resume .base, .resume .func {
  box-sizing: border-box;
  float: left;
}

.resume .base >,
.resume .func > {
  padding-bottom: 10px;
}

.resume .base > :last-of-type,
.resume .func > :last-of-type {
  padding-bottom: 0;
}

.resume .base {
  width: 225px;
  padding: 30px 15px;
  background: rgba(238, 238, 238, 0.6);
}

.resume .base .profile {
  background: #8d9e78;
  padding: 30px 15px 5px 15px;
  margin: -30px -15px 45px -15px;
  position: relative;
  z-index: 2;
}

.resume .base .profile::after {
  content: "";
  position: absolute;
  background: #8d9e78;
  width: 100%;
  height: 30px;
  bottom: -15px;
  left: 0;
  transform: skewY(-5deg);
  z-index: -1;
}

.resume .base .profile .photo img {
  width: 100%;
  border-radius: 50%;
}

.resume .base .profile .info {
  text-align: center;
  color: #fcfcfc;
}

.resume .base .profile .info .name {
  margin-top: 10px;
  margin-bottom: 0;
  font-size: 1.5em;
  font-weight: normal;
}

.resume .base .about {
  text-align: left;
}

.resume .base .contact {
  line-height: 24px;
  text-align: left;
}

.resume .base .contact a:hover {
  color: #e07a5f;
}

.resume .base .contact a:hover span::after {
  width: 100%;
}

.resume .base .contact :hover i {
  color: #e07a5f;
}

.resume .base .contact .icon {
  color: #8d9e78;
  width: 20px;
  height: 20px;
  font-size: 20px;
  text-align: center;
  margin-right: 15px;
  transition-duration: 0.3s;
}

.resume .base .contact span {
  position: relative;
}

.resume .base .contact span::after {
  content: "";
  position: absolute;
  background: #e07a5f;
  height: 1px;
  width: 0;
  bottom: 0;
  left: 0;
  transition-duration: 0.3s;
}

.resume .base .follow .box {
  text-align: center;
  vertical-align: middle;
}

.resume .base .follow .box a {
  display: inline-block;
  vertical-align: text-bottom;
}

.resume .base .follow .box a:hover .icon .norotate{
  transform: rotate(-45deg) scale(1.2);
}


.resume .base .follow .box a:hover .icon {
  background: #e07a5f;
  border-radius: 5px;
  transform: rotate(45deg) scale(0.8);
}


.resume .base .follow .box a:hover .icon::before {
  transform: rotate(-45deg) scale(1.2);
}


.resume .base .follow .box .icon {
  display: inline-block;
  font-size: 30px;
  background: #8d9e78;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  line-height: 60px;
  color: #fcfcfc;
  margin: 0 10px 10px 10px;
  transition-duration: 0.3s;
}

.resume .base .follow .box i::before {
  transition-duration: 0.3s;
}

.resume .base .follow .box .fa::before {
  display: block;
}

.resume .func {
  width: 645px;
  padding: 30px 25px;
}

.resume .func:hover {
  transition-duration: 0.3s;
}

.work:hover h3,
.edu:hover h3,
.skills-soft:hover h3,
.skills-prog:hover h3,
.interests:hover h3 {
  letter-spacing: 1.6px;
}

.work:hover h3 .icon,
.edu:hover h3 .icon,
.skills-prog:hover h3 .icon,
.skills-soft:hover h3 .icon,
.interests:hover h3 .icon{
  transform: scale(1.2);
}

.resume .func:hover > :not(:hover) {
  opacity: 0.5;
}

.resume .func h3 {
  transition-duration: 0.3s;
  margin-top: 0;
  text-align: left;
}

.resume .func h3 .icon {
  color: #fcfcfc;
  background: #8d9e78;
  width: 22px;
  height: 22px;
  font-size: 8px;
  line-height: 22px;
  border-radius: 50%;
  text-align: center;
  vertical-align: middle;
  margin-right: 8px;
  transition-duration: 0.3s;
  padding: 5px;
}

.resume .func .work,
.resume .func .edu {
  float: left;
}

.resume .func .work small,
.resume .func .edu small {
  display: block;
  opacity: 0.7;
}

.resume .func .work ul li,
.resume .func .edu ul li {
  position: relative;
  margin-left: 15px;
  padding-left: 25px;
  padding-bottom: 15px;
}

.resume .func .work ul li:hover::before,
.resume .func .edu ul li:hover::before {
  animation: circle 1.2s infinite;
}

.resume .func .work ul li:hover span,
.resume .func .edu ul li:hover span {
  color: #e07a5f;
}

@keyframes circle {
  from {
    box-shadow: 0 0 0 0px #3d405b;
  }

  to {
    box-shadow: 0 0 0 6px rgba(61, 64, 91, 0);
  }
}

.resume .func .work ul li:first-of-type::before,
.resume .func .edu ul li:first-of-type::before {
  width: 10px;
  height: 10px;
  left: -2px;
}

.resume .func .work ul li:last-of-type,
.resume .func .edu ul li:last-of-type {
  padding-bottom: 3px;
}

.resume .func .work ul li:last-of-type::after,
.resume .func .edu ul li:last-of-type::after {
  border-radius: 1.5px;
}

.resume .func .work ul li::before,
.resume .func .work ul li::after,
.resume .func .edu ul li::before,
.resume .func .edu ul li::after {
  content: "";
  display: block;
  position: absolute;
}

.resume .func .work ul li::before,
.resume .func .edu ul li::before {
  width: 7px;
  height: 7px;
  border: 3px solid #3d405b;
  background: #fcfcfc;
  border-radius: 50%;
  left: 0;
  z-index: 1;
}

.resume .func .work ul li::after,
.resume .func .edu ul li::after {
  width: 3px;
  height: 100%;
  background: #3d405b;
  left: 5px;
  top: 0;
}

.resume .func .work ul li span,
.resume .func .edu ul li span {
  transition-duration: 0.3s;
}

.resume .func .work {
  width: 42%;
}

.resume .func .edu {
  width: 58%;
}

.resume .func .skills-prog {
  clear: both;
}

.resume .func .skills-prog ul {
  text-align: left;
  margin-left: 15px;
}

.resume .func .skills-prog ul li {
  margin-bottom: 8px;
  display: flex;
  text-align: left;
  align-items: center;
  transition-duration: 0.3s;
}

.resume .func .skills-prog ul li:hover {
  color: #e07a5f;
}

.resume .func .skills-prog ul li:hover .skills-bar .bar {
  background: #e07a5f;
  box-shadow: 0 0 0 1px #e07a5f;
}

.resume .func .skills-prog ul li span {
  display: block;
  width: 120px;
}

.resume .func .skills-prog ul li .skills-bar {
  background: #cdcdcd;
  height: 2px;
  width: calc(100% - 120px);
  position: relative;
  border-radius: 2px;
}

.resume .func .skills-prog ul li .skills-bar .bar {
  position: absolute;
  top: -1px;
  height: 4px;
  background: #8d9e78;
  box-shadow: 0 0 0 #8d9e78;
  border-radius: 5px;
}

.resume .func .skills-soft ul {
  display: flex;
  justify-content: space-between;
  text-align: center;
}

.resume .func .skills-soft ul li {
  position: relative;
}

.resume .func .skills-soft ul li:hover svg .cbar {
  stroke: #e07a5f;
  stroke-width: 4px;
}

.resume .func .skills-soft ul li:hover span,
.resume .func .skills-soft ul li:hover small {
  transform: scale(1.2);
}

.resume .func .skills-soft ul li svg {
  width: 95%;
  fill: transparent;
  transform: rotate(-90deg);
}

.resume .func .skills-soft ul li svg circle {
  stroke-width: 1px;
  stroke: #cdcdcd;
}

.resume .func .skills-soft ul li svg .cbar {
  stroke-width: 3px;
  stroke: #8d9e78;
  stroke-linecap: round;
}

.resume .func .skills-soft ul li span,
.resume .func .skills-soft ul li small {
  position: absolute;
  display: block;
  width: 100%;
  top: 52%;
  transition-duration: 0.3s;
}

.resume .func .skills-soft ul li span {
  top: 40%;
}

.resume .func .interests-items {
  box-sizing: border-box;
  padding: 15px;
  width: 100%;
  border: 1px solid #cdcdcd;
  text-align: center;
  display: flex;
  justify-content: space-between;
  transform: scale(1.0);
}

.resume .func .interests-items .icon {
  display: inline-block;
  color: #8d9e78;
  padding: 10px;
  width: 60px;
  height: 60px;
}

.resume .func .interests-items :hover .icon {
  transition: 0.3s;
  transform: scale(1.2);
}

.resume .func .interests-items :hover span {
  color: #e07a5f;
  transition-duration: 0.3s;
}

.resume .func .interests-items i {
  font-size: 45px;
  width: 60px;
  height: 60px;
  line-height: 60px;
  color: #8d9e78;
  transition-duration: 0.3s;
}

.resume .func .interests-items i.guitar {
  display: block;
  margin: 0 auto;
}

.resume .func .interests-items i.guitar svg {
  width: 50px;
  height: 50px;
  margin-top: 5px;
  fill: #8d9e78;
}

.resume .func .interests-items span {
  display: block;
}
</style>