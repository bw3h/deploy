<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style>

@font-face {
  font-family: "Pirulen";
  src: local("Pirulen"),
   url(./fonts/pirulen.ttf) format("truetype");

} 

@font-face {
  font-family: "Alien";
  src: local("Alien"),
   url(./fonts/alien.ttf) format("truetype");

} 

@font-face {
  font-family: "Anita";
  src: local("Anita"),
   url(./fonts/anita.ttf) format("truetype");

} 

@font-face {
  font-family: "Computer";
  src: local("Computer"),
   url(./fonts/cmunbbx.ttf) format("truetype");

} 

@font-face {
  font-family:"Lato";
  src: local("Lato"),
   url(./fonts/lato.ttf) format("truetype");

} 

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  text-align: center;
  color: #ffffff;
  font-family: Helvetica;
}



.main {
  background: linear-gradient(to left,#24243e, #302b63, #24243e);

  

}

.boxe {
  width: 1440px;
  margin: 0 auto;

  


}
.statsD {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
  gap: 20px;
  margin: 12px;
}
.boxes {
display: grid;
grid-template-columns: 1.5fr 1fr;

}
@media only screen and (max-width: 560px) {

  .boxw {
    display: flex;
    justify-content: center;
    width: 480px;
    height:240px;
    padding: 36px;
    border-radius: 10px;
    box-shadow: 0 10px 40px #000;
    border-radius: 10px;
    border: 1px solid #00bfff;
    margin: 20px 40px 0px 40px;
    background-color: transparent;

}

.boxw {
  display: flex;
    justify-content: center;
    width: 480px;
    height:240px;
    padding: 36px;
    border-radius: 10px;
    box-shadow: 0 10px 40px #000;
    border-radius: 10px;
    border: 1px solid #00bfff;
    margin: 20px 40px 0px 40px;
    background-color: transparent;

}



  .vAddy1 {
  font-size: 12px;
  font-weight: 100;
  font-family: Pirulen, Arial, Helvetica, sans-serif;
  color:#ffffff;
  text-align: left;

}

.box-btn{
  display:flex;
padding-top: 4em;
}
.box3 {
  border-top-right-radius: 8px; 
  border-top-left-radius: 8px;
  width: auto;
  height: 48px;
  margin-top: 25px;
  margin-left: 20px;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
  border-top-right-radius: 10px;
}

.box4{
  border-top-right-radius: 8px; 
  border-top-left-radius: 8px;
  width: auto;
  height: 48px;
  margin-top: 25px;
  margin-left: 20px;
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
  border-top-right-radius: 10px;
}


.vAddy {
  font-size: 12px;
  color:#ffffff;
  text-align: left;

}





.boxes {

display:inline-table;
}

.contract-balance-available2 {
  margin-top: 10px;
  text-align: center;
  font-size: small;
}

.boxe {
  width: 100vw;
  margin: 0 auto;
}

.statsD {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 20px;
  margin: 12px 24px;
}

.dashboard {
   width: 100%;
   margin: 0 auto;
   position: fixed;
     top: 50%;
     left: 50%;
     transform: translate(-50%, -50%);
  }
.el-message-box {
  width: 268px;
}

.box0 {
  margin: 20px auto;
}






}

.box0 {
  width: auto;
  max-width: 1100px;  
  height: fit-content;
  border-width: 2px;
  background: #000;
  border-radius: 4px;
  margin: 20px 10px 20px 10px;  
  padding: 0 10px; 
  align-content: center; 
  justify-content: center;
  box-sizing: 1px;
  border-radius: 10px;
  box-sizing: 1px;
  border: none;
  border: 1px solid #ffffffa4;
  border-radius: 10px;
  box-shadow: 0 0 40px #00bfff31;

  
}



.boxw {
    display: flex;
    justify-content: center;
    width: 36rem;
    height: 24rem;
    padding: 36px;
    border-radius: 10px;
    box-shadow: 0 0 40px #000;
    border-radius: 10px;
    /* border: 1px solid #00bfff; */
    margin: 20px 40px 0px 40px;
    background-color: transparent;

}

.boxd {
  max-width: 1440px;
  min-height: 640px;
  padding-top: 10px; 
  background: transparent;
  display: flex;
  border-radius: 10px;
  margin: 0 auto;
  box-sizing: 1px;
  border: none;
  border-radius: 10px;
  box-shadow: 0 0 40px #000;
}

.box-btn {
  margin: 4rem auto;
  width: 16em;
  height: 24em;
  box-sizing: 1px;
  border: 1px solid ;
  border-radius: 10px;

}

.box2 {
  width: auto;
  min-height: 300px;
  padding-top: 10px; 
  background: transparent;
  display:grid;
  border-radius: 10px;
  margin: 50px 30px 0px 10px;
  box-sizing: 1px;
  border: none;
  border-radius: 10px;
  box-shadow: 0 0 40px #000;
}

.balance-box {
  width: 80em;
  padding-top: 10px; 
  background: transparent;
  display:grid;
  border-radius: 10px;
  margin: 2rem auto;
  box-sizing: 1px;
  border: none;
  border-radius: 10px;
  box-shadow: 0 0 40px #000;
}

.action-box1 {
  width: 80em;
  min-height: 300px;
  background: linear-gradient(to top,#3d00b9,#6f5fff);
  display:grid;
  border-radius: 10px;
  margin: 0 auto;
  box-sizing: 1px;
  border: none;
  border-radius: 10px;
  box-shadow: 0 0 40px #000;
}

.action-box2 {
  width: 80em;
  min-height: 300px;
  background: linear-gradient(to top,#3d00b9,#6f5fff);
  display:grid;
  border-radius: 10px;
  margin: 0 auto;
  box-sizing: 1px;
  border: none;
  border-radius: 10px;
  box-shadow: 0 0 40px #000;
}


.aw {
  color: rgba(102, 102, 102, 1);
  font-size: 34px;
}

.el-button {
  border-radius: 10px !important;
  font-weight:normal !important;
  font-family: Pirulen, Helvetica !important;
}
.el-message-box {
  border-radius: 10px !important;
  background: linear-gradient(to right,#6519c9,#2472fc) !important;
  font-family: Anita, Helvetica, sans-serif !important;
  border: none;
  box-shadow: 0 0 40px #000;
}

.el-message-box__content {
  color: #000000 !important;
  font-size: 1rem !important;
  font-weight:normal !important;
}

.el-message-box__message {
  text-align: center !important;
} 
.el-radio__input.is-checked + .el-radio__label {
  color: #ffffff !important;
}
.el-radio__input.is-checked .el-radio__inner {
  border-color: #ffffff !important;
  background: #ffffff !important;
}
.el-radio__inner:hover {
  border: 1px solid #ffffff !important;
}
.sk {
  color: rgba(102, 102, 102, 1);
  font-size: 16px;
  font-weight:normal;
  margin-top: 30px;
}
.skbtn {
  width: 416px;
  height: 50px;
  border-radius: 4px;
  border: 1px solid #ddd;
  line-height: 50px;
  cursor: pointer;
  color: #ddd;
  text-align: center;
  font-size: 14px;
}



.bg-box {
  overflow: hidden;
  height: 188px;
  width: 100%;
}
.el-input__inner {
  background-color: #000 !important;
}

.el-select .el-input.is-focus .el-input__inner {
  border-color: #ffffff !important;
}
.el-select .el-input__inner:focus {
  border-color: #ffffff !important;
}
.el-select-dropdown__item.selected {
  color: #ffffff !important;
}
.el-input.is-active .el-input__inner, .el-input__inner:focus {
  border-color: #ffffff !important;
}
.el-message-box__title{
 color: #ffffff !important;
 text-align: center !important;
 font-family: Pirulen, Helvetica !important;
}

.el-message-box__container {
  font-family: Pirulen, Helvetica !important;
}

.el-message-box__input {
  text-align: center !important;
}

.el-message-box__btns {
 text-align: center !important;
}
.el-input {
 width: 240px !important;
 margin: 0 auto !important;
}
.el-input__inner {
  border-radius: 10px !important;
  background-color: #2c3e50 !important;
  color: #ffffff !important;
  text-align: center !important;
  
}

.el-button--primary {
  font-size: 1rem;
  font-family: Anita, Helvetica, sans-serif;
  width: 8rem;
  font-weight: 200;
  height: 2.4rem;
  border-radius: 10px;
  color: #8D80FF;
  background: linear-gradient(to right,#24243e, #302b63, #24243e) !important;
  background-position: center;
  margin: 0 10px;
  border: none;
}

.el-button--default {
  font-size: 1rem;
  font-family: Anita, Helvetica, sans-serif;
  width: 8rem;
  font-weight: 200;
  height: 2.4rem;
  border-radius: 10px;
  color: #8D80FF;
  background: linear-gradient(to right,#24243e, #302b63, #24243e) !important;
  background-position: center;
  margin: 0 10px;
  border: none;
}

.p{
  max-width: 342px;
}


</style>
