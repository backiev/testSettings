<template>

   <div class="d-flex section">
      <div class="d-flex section-header align-start font-bold">
         <div>Оповещения о новых подборках</div>
      </div>
      <div class="section-content font-14px" >
         <div class="section-content__title">
            Выберите, куда будут приходить уведомления при появлении автомобилей, которые подходят под критерии вашей подборки
         </div>
         <div class="notification">
            <div class="notification-title">Уведомления</div>
            <div class="notification-fields">
               <div class="notification-fields__item">
                  <input type="radio" id="off" name="notification" value="off" v-model="picked">
                  <label for="off">Выкл</label>
               </div>
               <div class="notification-fields__item" >
                  <input type="radio" id="push" name="notification" value="Push" disabled>
                  <div class="d-flex justify-between w-100">
                     <label for="push">Push</label>
                     <div class="tippy">
                        <font-awesome-icon icon="fa-solid fa-circle-info" class="cursor-pointer" />
                        <div class="tippy-content">Можно установить только в приложении</div>
                     </div>
                  </div>
               </div>
               <div class="notification-fields__item">
                  <input type="radio" id="email" name="notification" value="Email" v-model="picked">
                  <div class="d-flex justify-between w-100 align-center">
                     <label for="email">Email</label>
                     <input type="text" class="input" v-show="emailOn" v-model="email" v-on:input="updateEmail">
                     <font-awesome-icon icon="fa-solid fa-pencil" class="cursor-pointer" v-show="!emailOn" @click="emailOn = !emailOn"/>
                  </div>
               </div>
               <div class="notification-fields__item">
                  <input type="radio" id="telegram" name="notification" value="Telegram" v-model="picked">
                  <div class="d-flex justify-between w-100 align-center">
                     <label for="telegram"><a href="#" class="link">Telegram</a></label>
                     <input type="text" class="input" v-show="telegramOn">
                     <font-awesome-icon icon="fa-solid fa-pencil" class="cursor-pointer" v-show="!telegramOn"  @click="telegramOn = !telegramOn"/>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
   export default {
      data () {
         return {
            email: this.emailOld,
            emailOn: false,
            telegramOn: false,
            picked: this.notifytype,
         }
      },
      props: {
         notifytype: {
            type: String
         },
         emailOld: {
            type: String
         }
      },
      methods: {
         updateEmail() {
            this.email.trim() ? this.$emit('update', this.email) : ' ';
         }
      }
   }
</script>

<style lang="sass" scoped>
.notification
   max-width: 290px
   &-fields
      display: flex
      flex-direction: column
      gap: 10px
      
      &__item
         display: flex
         gap: 5px
         align-items: center
         border-bottom: 1px solid #e1e1e3
         padding: 10px 0
</style>