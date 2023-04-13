<template>

   <div class="d-flex section">
      <div class="d-flex section-header align-start font-bold">
         <div>Переход в карточку</div>
      </div>
      <div class="section-content font-14px" >
         <div class="section-content__title">
            Выберите, каким образом будет открываться детальное представление выбранного вами транспорта.
         </div>
         <div class="notification">
            <div class="notification-fields">
               <div class="notification-fields__item" >
                  <input type="radio" id="current" name="card">
                  <div class="d-flex justify-between w-100">
                     <label for="current">В карточку в текущем окне</label>
                  </div>
               </div>
               <div class="notification-fields__item">
                  <input type="radio" id="another" name="card">
                  <div class="d-flex justify-between w-100 align-center">
                     <label for="another">В карточку в отдельном окне</label>
                  </div>
               </div>
               <div class="notification-fields__item">
                  <input type="radio" id="origin" name="card">
                  <div class="d-flex justify-between w-100 align-center">
                     <label for="origin">На источнник</label>
                     <div class="tippy">
                        <font-awesome-icon icon="fa-solid fa-circle-info" class="cursor-pointer" />
                        <div class="tippy-content">Прямой переход в объявление на источнике</div>
                     </div>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
   export default {
      
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
         border-bottom: 1px solid black
         padding: 10px 0

</style>