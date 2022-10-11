<template>
  <div class="about">
    <div class="hero is-info" >
      <div class="hero-body has-text-centered">
        <h1 class="title" >My Account</h1>
        <h2 class="subtitle">My Account Page</h2>
      </div>
    </div>
    <section class="section">
        <button class="button is-danger" @click="logout()" >Log out</button>
    </section>
  </div>
</template>

<script>

import axios from 'axios'

    export default {
        methods:{
            logout() {
                console.log('logout')

                axios.defaults.headers.common['Authorization'] = ""

                localStorage.removeItem('token')

                this.$store.commit('removeToken')

                this.$router.push('/')
            }
        }
    }
</script>
