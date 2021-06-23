<template>
  <div id="app">
    <div class="popup" id="js-popup" :class="{'open':isClass}">
      <div class="popup-inner">
          <div class="title">
            <p><img class="logo" src="./assets/logo.png" alt=""></p>
            <p class="title-text"><span class="red">BS</span><span class="blue">テレ東</span></p>
          </div>
          <div class="content">
            <p>{{month}}月{{day}}日（{{week}}）{{time}}</p>
            <p>カレンダー登録します。よろしいですか。</p>
          </div>
          <div class="two">
            <button class="yes">はい</button>
            <button class="no" id="back" @click="back()">いいえ</button>
          </div>
      </div>
      <div class="black-background" id="js-black-bg"></div>
    </div>
    <button class="register" @click="popup()" :class="{'active':isClass}">カレンダーに登録</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isClass: false,
      month: "",
      day: "",
      week: "",
      time: "",
    };
  },
  methods: {
    popup() {
      this.isClass = !this.isClass;
    },
    back() {
      this.isClass = !this.isClass;
    }
  }
};
</script>

<style>
html,
body,
div,
span,
object,
iframe,
h1,
h2,
h3,
h4,
h5,
h6,
p,
blockquote,
pre,
abbr,
address,
cite,
code,
del,
dfn,
em,
img,
ins,
kbd,
q,
samp,
small,
strong,
sub,
sup,
var,
b,
i,
dl,
dt,
dd,
ol,
ul,
li,
fieldset,
form,
label,
legend,
table,
caption,
tbody,
tfoot,
thead,
tr,
th,
td,
article,
aside,
canvas,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section,
summary,
time,
mark,
audio,
video {
  margin: 0;
  padding: 0;
  border: 0;
  outline: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}

body {
  line-height: 1.6;
}

article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
menu,
nav,
section {
  display: block;
}

nav ul {
  list-style: none;
}

blockquote,
q {
  quotes: none;
}

blockquote:before,
blockquote:after,
q:before,
q:after {
  content: "";
  content: none;
}

a {
  margin: 0;
  padding: 0;
  font-size: 100%;
  vertical-align: baseline;
  background: transparent;
}

/* change colours to suit your needs */
ins {
  background-color: #ff9;
  color: #000;
  text-decoration: none;
}

/* change colours to suit your needs */
mark {
  background-color: #ff9;
  color: #000;
  font-style: italic;
  font-weight: bold;
}

del {
  text-decoration: line-through;
}

abbr[title],
dfn[title] {
  border-bottom: 1px dotted;
  cursor: help;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
}

/* change border colour to suit your needs */
hr {
  display: block;
  height: 1px;
  border: 0;
  border-top: 1px solid #cccccc;
  margin: 1em 0;
  padding: 0;
}

input,
select {
  vertical-align: middle;
}

html {
  height: 100%;
}

a {
  color: #333333;
  text-decoration: none;
}

img {
  width: 100%;
  height: 100%;
  display: block;
}

.flex {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}

body {
  color: #333333;
  height: 100%;
}
.popup {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 9999;
  opacity: 0;
  visibility: hidden;
  transition: .6s;
}
.popup.open {
  opacity: 1;
  visibility: visible;
}
.popup-inner {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%);
  width: 80%;
  max-width: 750px;
  height: 250px;
  background-color: #fff;
  z-index: 2;
  text-align: center;
  border-radius: 30px;
  border: solid 3px #000;
}
.black-background {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,.8);
  z-index: 1;
  cursor: pointer;
}
.title p {
  display: inline-block;
  vertical-align: top;
}
.title {
  font-size: 60px;
}
.title img {
  width: 100px;
  height: 100px;
}
.content {
  font-size: 30px;
  line-height: 35px;
  color:#1378c0;
  font-weight: bold;
  margin-bottom: 15px;
}
.two button {
  background-color: #1378c0;
  height: 60px;
  width: 140px;
  color: white;
  border-radius: 15px;
  font-weight: bold;
  border: none;
}
.two button:hover {
  background-color: #1378c0a9;
}
.yes {
  margin-right: 30px;
}
.no {
  margin-left: 30px;
}
.red {
  color: #d60836;
}
.blue {
  color: #234574;
}
.register {
  background-color: yellow;
  border: none;
  border-radius: 25px;
  padding: 10px;
  font-weight: bold;
}
.register:hover {
  background-color: rgba(255, 255, 0, 0.575);
}
button {
  cursor: pointer;
}
@media screen and (max-width: 768px){
  .popup-inner {
    height: auto;
  }
  .two button {
    margin-bottom: 10px;
  }
  .title {
  font-size: 50px;
  }
  .title img {
    width: 90px;
    height: 90px;
  }
  .content {
    font-size: 25px;
    line-height: 30px;
  }
}
@media screen and (max-width: 480px){
  .popup-inner {
    height: auto;
  }
  .two button {
    margin-bottom: 10px;
    margin-right: 0;
    margin-left: 0;
  }
  .two {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .title {
  font-size: 40px;
  }
  .title img {
    width: 60px;
    height: 60px;
  }
  .content {
    font-size: 20px;
    line-height: 25px;
  }
  .two button {
    height: 50px;
    width: 140px;
  }
}
</style>
