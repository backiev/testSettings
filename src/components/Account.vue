<template>

   <div class="d-flex section">
      <div class="d-flex section-header align-start font-bold">
         <div>Учетная запись</div>
      </div>
      <div class="section-content fields font-14px" >
         <div class="fields-item" v-for="field in fields">
            <div class="fields-item__header">{{field.title}}</div>
            <div>
               <input class="fields-item__input input" :value="field.textInput" />
               <div class="fields-item__subtitle" v-show="field.subtitle ">{{ field.subtitle }}</div>
            </div>
            
         </div>
      </div>
   </div>

</template>

<script>
   export default {
      data() {
         return {
            fields: [
               { id: 0,  title: 'Компания', textInput: 'Частное ллицо', subtitle: ''},
               { id: 1,  title: 'Логин', textInput: '213123', subtitle: ''},
               { id: 2,  title: 'Номер телефона', textInput: '213123', subtitle: ''},
               { id: 3,  title: 'Имя', textInput: 'аноним', subtitle: ''},
               { id: 4,  title: 'Фамилия', textInput: '', subtitle: '* Не обязательно'},
            ]
         }
      }
   }
</script>

<style lang="sass" scoped>
.fields 
   width: 100%
   &-item 
      display: flex
      align-items: center
      margin-bottom: 16px
      &__header
         max-width: 96px
         width: 100%
         margin-right: 8px
      &__input 
         flex: 1

      &__subtitle
         margin-top: 4px
         color: #a3a3a3
         font-size: 12px
</style>