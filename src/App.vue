<template>
  <main>
    <h2>Настройки</h2>
    <Sip />
    <Account />
    <NotificationVue />
    <TransitionVue />
    <OtherVue />
    <div class="d-flex section">
      <div class="d-flex section-header align-start">
      </div>
      <div class="section-content w-100">
        <button class="w-100 btn">Сохранить</button>
      </div>
    </div>
    
  </main>
</template>

<script>
import Sip from './components/Sip.vue';
import Account from './components/Account.vue'
import NotificationVue from './components/Notification.vue';
import TransitionVue from './components/Transition.vue';
import OtherVue from './components/Other.vue'
export default {
  name: 'App',
  components: {
    Sip, Account, NotificationVue, TransitionVue, OtherVue
  }
}
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&display=swap')
body 
  background: #333
  color: white !important
  font-family: Montserrat, sans-serif !important
  padding: 0 15px
label, input[type=radio], input[type=checkbox]
  cursor: pointer
.d-flex 
  display: flex
.flex-grow 
  flex-grow: 1
.align-start
  align-items: start
.align-center
  align-items: center
.justify-between
  justify-content: space-between
.w-100
  width: 100%
.font-bold
  font-weight: bold
.font-14px
  font-size: 14px
.link
  color: green
  text-decoration: underline
.section
  margin-bottom: 32px
  &-header
    max-width: 200px
    width: 100%
    margin-right: 20px
  &-content
    max-width: 490px
    &__title
      color: #686869
      margin-bottom: 16px
      font-size: 14px
.btn
  background-color: #26a763
  color: white
  border: none
  border-radius: 2px
  padding: 13px 20px
  cursor: pointer

.input
  border: 1px solid #e1e1e3
  border-radius: 3px
  line-height: 11px
  box-sizing: border-box
  color: #222
  transition: all .3s
  padding: 8px 10px
  outline-color: green
  font-size: 14px
.cursor-pointer
  cursor: pointer
.tippy
   position: relative
   max-width: 350px
   bottom: 0px
   text-align: center
.tippy:hover
   .tippy-content
      display: block
.tippy-content
   display: none
   width: 300px
   position: absolute
   bottom: -20px
   left: -150px
   right: 0
   font-size: 12px
   line-height: 11px
   font-weight: 600
   background-color: #2dc574
   padding: 5px 10px
   border-radius: 2px
</style>
