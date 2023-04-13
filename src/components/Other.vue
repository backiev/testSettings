<template>
   <div class="d-flex section">
      <div class="section-header font-bold">
         <div>Прочие настройки</div>
      </div>
      <div class="section-content other font-14px" >
         <div class="d-flex justify-between other-time">
            <div>Часовой пояс</div>
            <div>
               <select name="select">
               <!--Supplement an id here instead of using 'name'-->
                  <option value="value1">Калиинград</option>
                  <option value="value2" selected>Москва</option>
                  <option value="value3">Самара</option>
                  <option value="value4">Екатериннбурд</option>
                  <option value="value5">Омск</option>
                  <option value="value6">Красоярск</option>
                  <option value="value7">Иркутск</option>
                  <option value="value8">Якутстк</option>
                  <option value="value9">Владивосток</option>
                  <option value="value10">Магадан</option>
                  <option value="value11">Камчатка</option>


               </select>
            </div>
         </div>
         <div class="other-fields">
            <div class="notification-fields__item" >
               <input type="checkbox" id="auto" name="notification">
               <div class="d-flex justify-between w-100">
                  <label for="auto">Автоматически переходить к новым обьявлениям</label>
                  <div class="tippy">
                     <font-awesome-icon icon="fa-solid fa-circle-info" class="cursor-pointer" />
                     <div class="tippy-content">Лента будет автоматически обновляться 1 раз в 3 секунды</div>
                  </div>
               </div>
            </div>
            <div class="notification-fields__item" >
               <input type="checkbox" id="colors" name="notification">
               <div class="d-flex justify-between w-100">
                  <label for="colors">Включить цвета в ленте</label>
                  <div class="tippy">
                        <font-awesome-icon icon="fa-solid fa-circle-info" class="cursor-pointer" />
                        <div class="tippy-content">Включение зеленого/желтого цвета</div>
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
.other
   max-width: 290px
   width: 100%
.notification-fields__item
   display: flex
   gap: 5px
   align-items: center
   // border-bottom: 1px solid black
   padding: 10px 0
   input 
      accent-color: green
</style>