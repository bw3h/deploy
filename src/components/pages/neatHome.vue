<template>
  <div class="dashboard">

    <div class="center-box">
      <div class="contract-description">
        web3heaven contract is a simple, secure, non-custodial browser contract.
      </div>

      <div class="boxe">
        <div class="boxes">
          <div class="boxw">
            <div class="lockked">
              <img src="../../assets/access.png" alt="Lock" class="lockimg" />
                </div>
            <div class="locked">Access your existing contract</div>
     
            <router-link to="/dashboard"><button class="ripp">ACCESS</button></router-link>
          </div>
          <div class="boxw">
            <div class="lockked">
             
              <img src="../../assets/create.png" alt="Lock" class="lockimg" />
            </div>
            <div class="locked">Create a brand new contract</div>
            <router-link to="/create"><button class="ripp">CREATE</button></router-link>
          </div>
        </div>
        <div v-if="step == 1">
          <Access @unlock="unlock"></Access>
        </div>
        <div v-if="step == 2" style="padding-bottom: 90px"></div>
      </div>
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
import { OrbitSpinner } from "epic-spinners";
import { LoopingRhombusesSpinner } from "epic-spinners";
import VideoBackground from 'vue-responsive-video-background-player';
import { Socket } from "vue-loading-spinner";
import Access from "./modules/access";
import EyeInput from "./modules/eyeInput";
import BigNumber from "bignumber.js";
import axios from "axios";

const Utils = require("web3heavenapi").utils;
const Nat = require("web3heavenapi").nat;
const Abi = require("web3heavenapi").abi;
const Web3 = require("web3");
const Utilss = require("web3").utils;
const URL = "https://rpc.web3heaven.net";
const web3 = new Web3("https://rpc.web3heaven.net");

export default {
  data() {
    return {
      currentChainId: '',
      chainId: '0x3e9',
      testChainId: '0x3ea',
      step: 2,
   
    };
  },
  components: {
    Access,
    EyeInput,
    OrbitSpinner,
    LoopingRhombusesSpinner,
    VideoBackground,
    Socket,
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

.pools {
  margin: 10px auto;
}

.btnss {
  margin-bottom: -10px;
}

.btns4 {
  margin-bottom: -20px;
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

.terms-of-use:hover {
  color: #000;  
  background: #ffffff radial-gradient(circle, transparent 1%, red 1%) center/15000%;
}

.rippleSelect {
  font-size: 12px;
  min-width: 68px;
  height: 22px;
  border-radius: 4px;
  font-weight: bold;
  color: #ffffff;
  border: 1px solid #ffffffa4;
  background-color: transparent;
  background-position: center;
  transition: background 0.4s;
  margin: 0 10px;
}

.rippleSelect:hover {
  color: #000;
  text-transform: uppercase;
  background: #ffffff radial-gradient(circle, transparent 1%, red 1%) center/15000%;
}

.rippleClaims {
  font-size: 12px;
  min-width: 68px;
  height: 22px;
  border-radius: 4px;
  font-weight: bold;
  border: 1px solid #ffffffa4;
  background-color: transparent;
  background-position: center;
  transition: background 0.4s;
  margin: 0 10px;
}

.rippleClaims:hover {
  color: #000;
  text-transform: uppercase;

  background: #ffffff radial-gradient(circle, transparent 1%, #ffffff 1%) center/15000%;
}

.deleg {
  text-align: center;
  margin: 10px 0px;
  font-size: 13px;
  font-weight: 100;
  color: #496785;
  font-family: Pirulen, Helvetica, sans-serif;
}

.noSel {
  text-align: center;

  margin: 10px 0px;
  font-size: 16px;
  font-weight: 100;
  color: #496785;
  font-family: Pirulen, Helvetica, sans-serif;
}

.addry-w {
  text-align: center;

  font-size: 16px;
  font-weight: 100;
  color: #496785;
  font-family: Pirulen, Helvetica, sans-serif;
}

.boxess {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  padding: 20px 0px;
}

.boxw {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction:column;
    width: 36rem;
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

  .rippleStake {
    font-size: 12px;
    min-width: 68px;
    height: 22px;
    border-radius: 4px;
    font-weight: bold;
    color: #ffffff;
    border: 1px solid #ffffffa4;
    background-color: transparent;
    background-position: center;
    transition: background 0.4s;
    margin: 0 auto;
  }

  .rippleStake:hover {
    color: #000;
    text-transform: uppercase;
    background: #ffffff radial-gradient(circle, transparent 1%, red 1%) center/15000%;
  }

  .rippleClaims {
    font-size: 12px;
    min-width: 68px;
    height: 22px;
    border-radius: 4px;
    font-weight: bold;
    border: 1px solid #ffffffa4;
    background-color: transparent;
    background-position: center;
    transition: background 0.4s;
    margin: 0 auto;
  }

  .rippleClaims:hover {
    color: #000;
    text-transform: uppercase;

    background: #ffffff radial-gradient(circle, transparent 1%, #ffffff 1%) center/15000%;
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


