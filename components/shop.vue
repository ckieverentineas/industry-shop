<!-- Please remove this file from your project -->
<template>
    <div id="main">
        <div id="alert">
                    <transition name="fade">
                        <p v-if="show">{{ message }}</p>
                        <p v-else></p>
                    </transition>
        </div>
        <div id="shop">
            <div v-for="item in items">
                <div id="shop-item">
                    <img src="block_energy.jpg" :tittle="item" :alt="item"/>
                    <label :tittle="item" :alt="item">{{ item }}</label>
                </div>
                <button v-on:click="addProduct(item)">Добавить в корзину</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      items:[   "Комлект оборудования для мастерской «Промышленная автоматика»",
                "Актуатор поворотного пере-ключателя с подсветкой 22мм",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод  24V UC красный с держателем ",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC зеленый с держателем",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC желтый с держателем",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог",
                "Контактор вспомогательный 4НО катушка управления 24В DC  или аналог",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог",
                "МОДУЛЬ БЛОК-КОНТАКТОВ, 2НО+2НЗ: 1НО, 1НЗ, 1НЗ, 1НО, Д. ВСПОМ. КОНТАКТОРОВ И КОНТАКТОРОВ ДЛЯ КОМ-МУТАЦИИ ЭЛЕКТРОДВИГА-ТЕЛЕЙ, ТИПОРАЗМЕР S00-S2, ВИНТОВЫЕ КЛЕММЫ",
                "Реле времени",
                "Клемма 4мм.кв 6.2мм серая",
                "Клемма 4мм.кв 6.2мм синяя",
                "Клемма 4мм.кв 6.2мм Ж/З –желто-зеленая",
                "Coverterminal  или аналог",
                "Through-type terminals (gray, 5.2mm)  илианалог",
                "Jumperplug (5 divisions) или аналог",
                "Таблички длинные 1 - 10, раз-мер ZB5",
                "Таблички длинные 11 - 20, раз-мер ZB5",
                "Таблички длинные 1 - 10, раз-мер ZB6",
                "Блок питания 24 V/4 A"
            ],
    show: false,
    cart: [],
    message: ""
    };
  },
  computed: {
    Checker() {
        
        
    }
  },
  methods: {
    addProduct(item) {
      this.cart += item
      this.show = true;
      this.message = `Добавлен в корзину товар ${item}`
      setTimeout(function(){ 
            if (this.show) {
                this.show = false
                this.message = ""
            }
        },1000);
    }
  }
};
</script>

<style scoped>
#shop {
    align-content: center;
    display: flex;
    overflow: hidden
}
#shop-item {
    width: 200px;
    height: 200px;
    box-sizing: border-box;
        flex: 1 0 250px;
        margin: 1rem;
        padding: 1rem;
        border: 1px solid #000;
        border-radius: 5px;
    overflow: hidden;
}
button {
    text-align: center;
    align-content: center;
    width: 200px;
    padding: 1rem;
    margin: 1rem;
}
img {
    width:170px;
    height:100px;

}
div { 
    flex-flow: row wrap;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active до версии 2.1.8 */ {
  opacity: 0;
}
#alert {
    text-align: center;
}
</style>