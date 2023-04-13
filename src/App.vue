<template>
  <main v-if="user.login">

    <h2>Настройки</h2>

    <Sip :sip="user.turbosip" />

    <Account  :companyname="user.companyname" :login="user.login" :phone="user.phone" :fname="user.fname" :lname="user.lname"/>

    <NotificationVue :notifytype="user.notifytypestring" :emailOld="user.email" @update="updateEmail"/>

    <TransitionVue :redirecttarget="user.redirecttarget" />

    <OtherVue :locklentaupdate="user.locklentaupdate" :colorlenta="user.colorlenta" :timezonestring="user.timezonestring"/>

    <div class="d-flex section">
      <div class="d-flex section-header align-start">
      </div>
      <div class="section-content w-100">
        <button class="w-100 btn" @click="handlerSubmit">Сохранить</button>
      </div>
    </div>
    <transition name="fade">
      <div class="modal" v-show="showModal">
        Сохранено
      </div>
    </transition>
    

  </main>
</template>

<script>
import Sip from './components/Sip.vue';
import Account from './components/Account.vue'
import NotificationVue from './components/Notification.vue';
import TransitionVue from './components/Transition.vue';
import OtherVue from './components/Other.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    Sip, Account, NotificationVue, TransitionVue, OtherVue
  },
  data () {
    return {
      user: {},
      newEmail: '',
      showModal: false
    }
  },
  mounted () {
    axios.get('https://api.av100.ru/v3/user/2011999', {
      headers: {
        'X-Api-Key': '8bcfb6e1-4fa8-4fae-872c-a435bbdbe8d9', 
        'X-User-Token': 'f9f3bcfd-fea3-4138-98a6-ae219638d0f9', 
        'X-Device-OS': '8bcfb6e1-4fa8-4fae-872c-a435bbdbe8d9'
      }
    })
      .then(response => (this.user = response.data))
      .catch(error => console.log(error));
  },
  methods: {
    updateEmail (value) {
      this.newEmail = value;
    },
    handlerSubmit () {
      axios.put('https://api.av100.ru/v3/user/2011999', 
        {
          "email": this.newEmail,
        },
        {
          headers: {
            'X-Api-Key': '8bcfb6e1-4fa8-4fae-872c-a435bbdbe8d9', 
            'X-User-Token': 'f9f3bcfd-fea3-4138-98a6-ae219638d0f9', 
            'X-Device-OS': '8bcfb6e1-4fa8-4fae-872c-a435bbdbe8d9'
          }
      })
      this.showModal = true;
      setTimeout(() => {
        this.showModal = false;
      }, 1000);
    },
  },
  
}
</script>

<style lang="sass">
@import './styles/main'
</style>
