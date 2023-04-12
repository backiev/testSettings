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
        <button class="w-100">Сохранить</button>
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

.input
  border: 0.1rem solid #e1e1e3
  border-radius: 0.3rem
  color: #222
  outline: none
  transition: all .3s
  padding: 0.8rem 1rem
</style>
