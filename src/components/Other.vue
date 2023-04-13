<template>
   <div class="d-flex section">
      <div class="section-header font-bold">
         <div>Прочие настройки</div>
      </div>
      <div class="section-content other font-14px" >
         <div class="d-flex justify-between other-time">
            <div>Часовой пояс</div>
            <div>
               <select v-model="selected">
                  <option v-for="option in options" :value="option.value">
                     {{ option.text }}
                  </option>
               </select>
            </div>
         </div>
         <div class="other-fields">
            <div class="notification-fields__item" >
               <input type="checkbox" id="auto" name="notification" v-model="lentaChecked">
               <div class="d-flex justify-between w-100">
                  <label for="auto">Автоматически переходить к новым обьявлениям</label>
                  <div class="tippy">
                     <font-awesome-icon icon="fa-solid fa-circle-info" class="cursor-pointer" />
                     <div class="tippy-content">Лента будет автоматически обновляться 1 раз в 3 секунды</div>
                  </div>
               </div>
            </div>
            <div class="notification-fields__item" >
               <input type="checkbox" id="colors" name="notification" v-model="colorChecked">
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
      data () {
         return {
            colorChecked: this.colorlenta,
            lentaChecked: !this.locklentaupdate,
            selected: this.timezonestring,
            options: [
               { text: 'Калининград', value: 'Kaliningrad' },
               { text: 'Москва', value: 'Moscow' },
               { text: 'Самара', value: 'Samara' },
               { text: 'Екатеринбург', value: 'Ekb' },
               { text: 'Омск', value: 'Omsk' },
               { text: 'Красноярск', value: 'Krasnoyarsk' },
               { text: 'Иркутск', value: 'Irkutsk' },
               { text: 'Якутск', value: 'Yakutsk' },
               { text: 'Владивосток', value: 'Vladivostok' },
               { text: 'Магадан', value: 'Magadan' },
               { text: 'Камчатка', value: 'Kamchatka' },
            ]
         }
      },
      props: {
         colorlenta: {
            type: Boolean
         },
         locklentaupdate: {
            type: Boolean
         },
         timezonestring: {
            type: String
         }
      }
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