<template>
  <div class="dashboard">

    <div class="center-box">
      <div class="contract-description">
        Please make sure the URL is: <span style="color: #8d80ff">contract.web3heaven.net</span>
      </div>    
        
          <div class="boxw">
            <div class="lockked">
              <img src="../../assets/unencrypted.png" alt="Lock" class="lockimg" />
                </div>
            <div class="locked" v-show="address == null">Unencrypted PrivKey</div>
     
            <button class="ripp" @click="gencontract">create</button>
            <div class="addy">{{ address }}  </div> <button   class="ripple"   @click="downloadPrivKey" v-show="address != null" >   SAVE   </button>     </div> 
          
  
       
    




            <div v-if="showModal" class="modal">
              <div class="modal-content">
                <span class="close" @click="closeModal">&times;</span>
                <div class="warning-texth">Dear User,</div>
                <div class="warning-text">
                Your PrivateKey is essential for accessing and securing your account. 
                Please ensure you have downloaded and securely stored your PrivateKey in a safe location. 
                Failure to do so will result in the loss of access to your account.</div>
                <div class="warning-text">Here are steps to safeguard your PrivateKey:</div>
                <div class="warning-text"> 1. Download Your PrivateKey: Click the [ SAVE ] button to retrieve your PrivateKey file.</div>
                <div class="warning-text">2. Store Securely: Save this file in a secure and backed-up location, such as an encrypted USB drive.</div>
                <div class="warning-text">3. Do Not Share: Never share your PrivateKey with anyone. Treat it as sensitive information.</div>
                <div class="warning-textn">Important Note: We cannot recover your PrivateKey if lost. Please take the necessary precautions to protect it.</div>
                <button   class="ripplem"   @click="closeModal">   OK, I Understand   </button>

              </div>
            </div>
        <div v-if="step == 1">
          <Access @unlock="unlock"></Access>
        </div>
        <div v-if="step == 2" style="padding-bottom: 90px"></div>
 
      <div class="contract-terms">
        By using this application you agree to the
        <router-link to="/terms">
          <button class="terms-of-use">Terms Of Use</button>
        </router-link>.
      </div>
    </div>
  </div>
</template>

<script>

import VideoBackground from 'vue-responsive-video-background-player';
import { Socket } from "vue-loading-spinner";
import Access from "./modules/access";
import EyeInput from "./modules/eyeInput";


const neatAccount = require("web3heavenapi").account;



export default {
  data() {
    return {
      showModal: true,
      currentChainId: '',
      chainId: '0x3e9',
      testChainId: '0x3ea',
      step: 2,
      address: null, 
      privKey: null
   
    };
  },
  components: {
    Access,
    EyeInput, 
    VideoBackground,
    Socket,
  },
  methods: {
    closeModal() {
      this.showModal = false;
      
    },
    gencontract() {
      const account = neatAccount.create();
      const address = account.address;
      const privKey = account.privateKey;
      this.account = account;
      this.address = address;
      this.privKey = privKey;
    },

    downloadPrivKey() {
      const linkNode = document.createElement("a");
      linkNode.download = this.account.address;
      linkNode.style.display = "none";
      const blob = new Blob([JSON.stringify(this.privKey)]);
      const cleanKey = blob.slice(3, 67);
      linkNode.href = URL.createObjectURL(cleanKey);
      document.body.appendChild(linkNode);
      linkNode.click();
      document.body.removeChild(linkNode);
    },
  },
}
</script>

<style scoped>
button {
  border: none;
  min-width: 36px;
  font-family: Anita, Helvetica, sans-serif;
  text-transform: uppercase;
  cursor: pointer;
  color: #ffffff;
  background-color: #273546;
  border-radius: 4px;
  outline: none;
  align-items: center;
  margin: 10px auto;
}

.modal {
  display: block;
  position: fixed;
  overflow: hidden;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.5); 
}

.modal-content {
  color: #8D80FF;
  font-weight:lighter;
  font-family: Lato, Helvetica, sans-serif;
  background-color: #000;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid rgb(141, 128, 255);
  border-radius: 10px;
  width: 80%;
}

.close {
  color: #8d80ff;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #6f5fff;
  text-decoration: none;
  cursor: pointer;
}

.contract-description {
  padding: 4em;
  font-size: 1.6rem;
  font-weight: 300;
  color: #ffffff;
  font-family: Anita, Helvetica, sans-serif;
}


.locked {
  text-align: center;
  margin: 20px;
  color: #ffffff;
  font-weight: 200;
  font-size: 1.4rem;
  font-family: Anita, Helvetica, sans-serif;

}

.lockked {
  align-items: center;
  justify-content: center;
}

.lockimg {
  width: 124px;
  height: auto;
  display: block;
  margin-top: 40px;
  margin-left: auto;
  margin-right: auto;
}

.warning-text {
  text-align: left;
  margin: 0.4rem;
}

.warning-textn {
  text-align: left;
  margin: 1rem 0.4rem;
  color: #a044ff;
}

.warning-texth {
  text-align: center;
  margin: 1rem;
  color: #8D80FF;
}

.center-box {
  text-align: center;
  margin: 0;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.contract-terms {
  color: rgb(141, 128, 255);
  font-family: Anita, Helvetica, sans-serif;
  font-weight: normal;
}





.dashboard {
  font-weight: bold;
  color: #ffffff;
  padding-top: 10px;
}


.addy{
  font-family: Anita, Helvetica, sans-serif;
  font-size: 1.2rem;
  display: inline;
  background-color: #ffffff;
  background-size: 100%;
  background-repeat: repeat;
  background-image: linear-gradient(to right, #a044ff, #46bbf4, #2472fc);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent
}

.ripp {
  font-size: 1.4rem;
  font-family: Anita, Helvetica, sans-serif;
  width: 12rem;
  height: 4rem;
  border-radius: 10px;
  color: #fff;
  background: linear-gradient(to right,#3d00b9,#8d80ff);
  background-position: center;
  margin: 40px;
}

.ripp:hover {
  color: #fff;
  text-transform: uppercase;
  background: #5340af;
}

.terms-of-use {
  font-size: 14px;
  width: 8rem;
  height: 22px;
  border-radius: 4px;
  margin-left: -10px;
  text-transform: lowercase;
  color: #ffffff;
  background-color: transparent;
  background-position: center;
  transition: background 0.4s;

}

.ripple {
  font-size: 1rem;
  font-family: Anita, Helvetica, sans-serif;
  width: 8rem;
  height: 2rem;
  border-radius: 10px;
  color: #fff;
  background: #6f5fff;
  background-position: center;
  margin: 0.4rem;
}

.ripple:hover {
  color: #fff;
  text-transform: uppercase;
  background: #495cff radial-gradient(circle, transparent 1%, #00bfff 1%) center/15000%;
}

.ripplem {
  font-size: 1rem;
  font-family: Anita, Helvetica, sans-serif;
  text-transform: none;
  width: 12rem;
  height: 2rem;
  border-radius: 10px;
  color: #fff;
  background: #6f5fff;
  background-position: center;
  margin: 0.4rem;
}

.ripplem:hover {
  color: #fff;
  /* text-transform: uppercase; */
  background: #495cff radial-gradient(circle, transparent 1%, #00bfff 1%) center/15000%;
}


.terms-of-use:hover {
  color: #000;  
  background: #ffffff radial-gradient(circle, transparent 1%, red 1%) center/15000%;
}




.boxw {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction:column;
    width: 72rem;
    height: auto;
    padding: 36px;
    border-radius: 10px;
    box-shadow: 0 0 40px #000;
    border-radius: 10px;
    margin: 20px 40px 0px 40px;
    background-color: transparent;

  }


@media only screen and (max-width: 560px) {
  .boxw {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: row;
    width: 480px;
    height: 240px;
    padding: 36px;
    border-radius: 10px;
    box-shadow: 0 10px 40px #000;
    border-radius: 10px;
    border: 1px solid #00bfff;
    margin: 20px 40px 0px 40px;
    background-color: transparent;

  }


  .pools {
    text-align: center;
    margin: 0 auto;
    padding: 10px;
  }



  #myGrid {
    flex: 1 1 0px;
    width: 100%;
  }

  .box2 {
    margin: 60px 10px;
  }
}
</style>


