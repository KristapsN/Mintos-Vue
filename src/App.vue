<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-6 col-xs-offset-3">
        <div class="curency--wrapper">
          <div class="row">
            <div class="col-xs-12 ceckbox--content--wrapper">
              <div
                v-for="(value, key) in checkedNames"
                :key="key"
                class="ceckbox--tag--wrapper"
              >
                <CurrencyTag
                  :currencyName="value"
                  @onClick="deleteHandler(key)"
                />
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col-xs-12 ceckbox--content--wrapper justy-content">
              <div
                v-for="{ id, name } in curnecys"           
                :key="id"
                class="checkbox--wrapper"
                :class="{ 'checked': aa === true }"
              >    
                <!-- <CurrencyCheck :currencyName="name" v-model:currencyName="checkedNames" /> -->
                <label class="checkbox" :for="id">
                  <input
                    class="checkbox__input"
                    type="checkbox"
                    :id="id"
                    :value="name"
                    v-model="checkedNames" 
                  />
                  <div className="checkbox__checkbox"><span>x</span></div>
                  {{ name }}</label                
                >
              </div>
            </div>
          </div>
        </div>
       
      </div>
    </div>
  </div>
</template>

<script>
import "flexboxgrid";
import CurrencyTag from "./components/currencyTag.vue";

export default {
  components: {
    CurrencyTag,
  },

  data() {
    return {
      aa: false,
      checkedNames: [],
      curnecys: [
        { id: "1", name: "EUR", checked1: true },
        { id: "2", name: "PLN", checked1: false },
        { id: "3", name: "GEL", checked1: false },
        { id: "4", name: "DKK", checked1: false },
        { id: "5", name: "CZK", checked1: false },
        { id: "6", name: "GBP", checked1: false },
        { id: "7", name: "SEK", checked1: false },
        { id: "8", name: "USD", checked1: false },
        { id: "9", name: "RUB", checked1: false },
      ],
    };
  },
  methods: {
    deleteHandler(key) {
      this.checkedNames.splice(key, 1);
      console.log(key);
    },
  },
};
</script>

<style scoped>
@import "./app.scss";
</style>
