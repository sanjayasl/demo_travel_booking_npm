<template>
<div>
  <div class="topnav">
    <div class="topleft">
      <img v-bind:src="url_l"/>
    </div>
    <div class="topright">
      <img v-bind:src="url_r"/>
    </div>
  </div>
  <div class="content">
    <h1 class="title1">{{title}}</h1>
    <div v-for="option in options" :key="option.name">
      <div v-bind:class="loadStyle(option)">
        <div class="left_content">
          <div style="float: left;font-size: 120%;"><strong>{{option.name}}</strong></div><br>
          <div style="float: left;">{{option.policy}}</div>
        </div>
        <div class="right_content">
          <QuantityButton></QuantityButton>
        </div>
      </div>
    </div>
    <div class="submission">
      <button class="button_submit">Continue</button>
    </div>
  </div>
</div>
</template>

<script>
import Components from "creative-library"
// import 'creative-library/dist/creative.css';
export default {
    name: 'Booking',
    data () {
      return {
        url_l: 'https://github.com/google/material-design-icons/blob/master/action/1x_web/ic_stars_white_48dp.png?raw=true',
        url_r: 'https://github.com/google/material-design-icons/blob/master/navigation/1x_web/ic_close_white_48dp.png?raw=true',
        title: 'Who is travelling?',
        options: [
          {name: 'Adult', policy: "16 years and over"},
          {name: 'Child', policy: "4-15 years"},
          {name: 'Infant', policy: "0-3 years"}
        ]
      }
    },
    methods: {
      loadStyle: function (option) {
        if(option.name == 'Adult'){
          return 'options_first';
        } else if (option.name == 'Infant') {
          return 'options_last';
        } else {
          return 'options';
        }
      }
    }
}
</script>

<style src='creative-library/dist/creative.css'></style>
<style>
.topnav {
  margin: 0;
  padding: 0;
  min-height: 54px;
  background-color:gainsboro;
  overflow: hidden;
}
.topleft {
  padding-left: 1%;
  float: left;
}
.topright {
  padding-right: 1%;
  float: right;
}
.content {
  display: inline;
  /* float: none;
  justify-content: center; */
}
.options {
  width: 480px;
  height: 60px;
  margin: auto;
  position: relative;
  border: 1px solid black;
}
.options_first {
  width: 480px;
  height: 60px;
  margin: auto;
  position: relative;
  border-radius: 5px 5px 0px 0px;
  border-left: 1px solid black;
  border-right: 1px solid black;
  border-top: 1px solid black;
}
.options_last {
  width: 480px;
  height: 60px;
  margin: auto;
  position: relative;
  border-radius: 0px 0px 5px 5px;
  border-left: 1px solid black;
  border-right: 1px solid black;
  border-bottom: 1px solid black;
}
.left_content {
  position: absolute;
  top: 50%;
  left: 0;
  padding-left: 10px;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
  /* background-color: blue; */
}
.right_content {
  position: absolute;
  top: 50%;
  right: 0;
  padding-right: 10px;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
  /* background-color: gold; */
}
.title1 {
  /* margin-top: 60px;
  margin-bottom: 50px; */
  font-size: 45px;
  text-align: center;
  margin: auto;
  padding-top: 60px;
  padding-bottom: 50px;
  position: relative;
}
.submission {
  margin: auto;
  position: relative;
  padding-top: 60px;
}
.button_submit {
  width: 480px;
  height: 60px;
  position: absolute;
  left: 50%;
  -ms-transform: translateX(-50%);
  transform: translateX(-50%);
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  text-align: center;
  text-decoration: none;
  /* display: inline-block; */
  font-size: 16px;
}
.button_submit:hover {
  background-color: white; 
  color: black; 
  border: 2px solid #4CAF50;
}
@media screen and (max-width: 600px) {
  .options {
    width: 380px;
    height: 60px;
    margin: auto;
    position: relative;
    border: 1px solid black;
  }
  .options_first {
    width: 380px;
    height: 60px;
    margin: auto;
    position: relative;
    border-radius: 5px 5px 0px 0px;
    border-left: 1px solid black;
    border-right: 1px solid black;
    border-top: 1px solid black;
  }
  .options_last {
    width: 380px;
    height: 60px;
    margin: auto;
    position: relative;
    border-radius: 0px 0px 5px 5px;
    border-left: 1px solid black;
    border-right: 1px solid black;
    border-bottom: 1px solid black;
  }
  .button_submit {
    width: 380px;
    height: 60px;
    position: absolute;
    left: 50%;
    -ms-transform: translateX(-50%);
    transform: translateX(-50%);
    background-color: #4CAF50; /* Green */
    border: none;
    color: white;
    text-align: center;
    text-decoration: none;
    /* display: inline-block; */
    font-size: 16px;
  }
  .title1 {
    font-size: 25px;
    text-align: center;
    margin: auto;
    padding-top: 30px;
    padding-bottom: 25px;
    position: relative;
  }
}
</style>