<script>
import { mapActions } from 'pinia';
import {useCounterStore} from "../stores/counter"
export default {
    data(){
        return {
            value : {
                email : "",
                password : ""
            }
        }
    },
    methods : {
        ...mapActions(useCounterStore, ['handleRegister'])
    }
}
</script>

<template>
    <!-- REGISTER PAGE -->
 <div id="pageContent-Register">
  <div class="d-flex align-items-center h-100">
    <div class="container">
      <div class="row">
        <div class="col-xl-4 col-lg-5 mt-5 col-md-6 col-sm-8 col-xs-12 ms-auto">
          <div class="bg-white rounded shadow-lg">
            <h1 class="text-center h5 pt-5 pb-3"><strong>REGISTER</strong></h1>
            <form class="py-2" @submit.prevent="handleRegister(this.value)">
              <div class="position-relative maxWidth320 px-2">
                <div class="inlineLogo"><i class="text-accent fas fa-at"></i></div>
                <input type="email" placeholder="enter your email here..." class="border-0  w-100" v-model="value.email" />
              </div>
              <div class="position-relative maxWidth320 px-2 d-flex align-items-end justify-content-between">
                <div>
                  <div class="inlineLogo"><i class="text-accent fas fa-key"></i></div>
                  <input type="password" placeholder="enter your password here..." class="border-0  w-100" v-model="value.password" />
                </div>
              </div>
              <div id="submitBtn" class="text-center">
                <button type="submit" class="btn w-50 btn-lg shadow-sm rounded-pill">Register</button>
              </div>
            </form>
            <div class="text-center pb-4">
              Have an account? <a href="#" @click.prevent="this.$router.push('/login')">Login</a>
            </div>
          </div>
          <div class="p-2 mx-2 rounded-bottom shadow bg-accent border-bottom border-dark"></div>
          <div class="p-1 mx-3 rounded-bottom shadow bg-accent"></div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<style>
#pageContent-Register {
    background : url('https://assets.hyatt.com/content/dam/hyatt/hyattdam/images/2022/08/21/0036/CGKPH-P0043-The-Spa-Couple-Treatment-Room.jpg/CGKPH-P0043-The-Spa-Couple-Treatment-Room.16x9.jpg?imwidth=1280') no-repeat;
    background-size : cover;
    background-position: center;
    height:100vh;
    width:100%;
  }
  input {
    height:64px;
    outline : none;
    padding-left:32px;
  }
  .inlineLogo {
    position : absolute;
    line-height:64px;
  }
  .text-accent {
    color:black
  }
  .bg-accent {
    background-color:black
  }
  #submitBtn {
    margin-top:64px;
    margin-bottom: 32px;
    border-top : 1px dashed #eaeaea;
  }
#submitBtn button {
    margin-top:-28px;
    /* Permalink - use to edit and share this gradient: https://colorzilla.com/gradient-editor/#f7644a+0,e73827+100 */
    background: rgb(3, 3, 3); /* Old browsers */
    background: -moz-linear-gradient(-45deg,  rgb(0, 0, 0) 0%, rgb(0, 0, 0) 100%); /* FF3.6-15 */
    background: -webkit-linear-gradient(-45deg,  rgb(0, 0, 0) 0%,rgb(0, 0, 0) 100%); /* Chrome10-25,Safari5.1-6 */
    background: linear-gradient(135deg,  rgb(0, 0, 0) 0%,rgb(0, 0, 0)0%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#f7644a', endColorstr='#e73827',GradientType=1 ); /* IE6-9 fallback on horizontal gradient */
    color:#fff;
  }
  .maxWidth320 {
    max-width:320px;
    margin: 0 auto;
  }
</style>
