<template>

   <div class="d-flex section">
      <div class="d-flex section-header align-start font-bold">
         <div>Звонок через SIP</div>
         <input type="checkbox" v-model="handlerChecked"
            true-value="on"
            false-value="off"
         >
      </div>
      <div class="section-content font-14px">
         <div class="section-content__title">
            Включите эту функцию чтобы Авито и другие площадки не блокировали ваш аккаунт. Будет выглядеть так, будто звонки совершаются с разных номеров.
         </div>
      </div>
   </div>

</template>

<script>
   export default {
      props: {
         sip: {
            type: String
         }
      },
      computed: {
         handlerChecked () {
            return this.sip;
         }
      }
   }
</script>

<style lang="scss" scoped>

</style>