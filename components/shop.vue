<!-- Please remove this file from your project -->
<template>
    <div id="main">
        <div v-if="aboutyes">
                <a href="/" class="overlay" id="b"></a>
                <div class="window">
                    <div id="alert">
                        <transition name="fade">
                            <p v-if="show">{{ message }}</p>
                            <p v-else></p>
                        </transition>
                    </div>
                    {{ item }}
                    {{ value }}
                    <button v-on:click="addProduct(item)">Добавить в корзину</button>
                </div>
                <a class="close" title="Закрыть" href="/"></a>
        </div>
        <div id="shop">
            <div v-for="(value, item) in items">
                <button v-on:click="getProduct(item, value)">Подробнее</button>
                <div>
                    <div id="shop-item">
                        <img src="block_energy.jpg" :tittle="item" :alt="item"/>
                        <label :tittle="item" :alt="item">{{ item }}</label>
                    </div>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            items: {
                "Комлект оборудования для мастерской «Промышленная автоматика»": "1",
                "Актуатор поворотного пере-ключателя с подсветкой 22мм": "",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод  24V UC красный с держателем ": "",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC зеленый с держателем": "",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC желтый с держателем": "",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог": "",
                "Контактор вспомогательный 4НО катушка управления 24В DC  или аналог": "",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог": "",
                "МОДУЛЬ БЛОК-КОНТАКТОВ, 2НО+2НЗ: 1НО, 1НЗ, 1НЗ, 1НО, Д. ВСПОМ. КОНТАКТОРОВ И КОНТАКТОРОВ ДЛЯ КОМ-МУТАЦИИ ЭЛЕКТРОДВИГА-ТЕЛЕЙ, ТИПОРАЗМЕР S00-S2, ВИНТОВЫЕ КЛЕММЫ": "",
                "Реле времени": "",
                "Клемма 4мм.кв 6.2мм серая": "",
                "Клемма 4мм.кв 6.2мм синяя": "",
                "Клемма 4мм.кв 6.2мм Ж/З –желто-зеленая": "",
                "Coverterminal  или аналог": "",
                "Through-type terminals (gray, 5.2mm)  илианалог": "",
                "Jumperplug (5 divisions) или аналог": "",
                "Таблички длинные 1 - 10, раз-мер ZB5": "",
                "Таблички длинные 11 - 20, раз-мер ZB5": "",
                "Таблички длинные 1 - 10, раз-мер ZB6": "",
                "Блок питания 24 V/4 A": ""
            },
    show: false,
    cart: [],
    message: "",
    aboutyes: false
    };
  },
  computed: {
    Checker() {
        
        
    }
  },
  methods: {
    async addProduct(item) {
      this.cart += item
      this.show = true;
      this.message = `Добавлен в корзину товар ${item}`
      setTimeout(function(){ 
            if (this.show) {
                this.show = false
                this.message = ""
            }
        },1000);
    },
    async getProduct(item, value) {
        this.aboutyes = true
        this.item = item
        this.value = value
        document.location.href= await "/#b"
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

/*Затемнение дисплея*/
.overlay {
    background-color: rgba(1, 0, 0, 0.77);
    right: 0;
    left: 0;
    position: fixed; 
    top: 0;
    bottom: 0;
    z-index: 11;
    display: none;
}
/*Слой становится видимым*/
.overlay:target {
    display: block;
}
/*Растягиваю картинку на всю ширину попапа*/
.window img { 
   width: 100%;
}
/*Характеристики самого окна, которое появляется после клика на кнопке*/
.window {
    left: 50%;
    z-index: 12;
    margin: 0;
    position: fixed;
    padding: 15px;
    border: 1px solid #383738;
    background: #fefeff;
    border-radius: 15px;
    box-shadow: 0 13px 21px rgba(0,1,0,.19),0 21px 63px rgba(0,1,0,.31);
    transform: translate(-50%, -450%);
    transition: transform 0.6s ease-out;
}
/*Появление модального окошка с верхнего края экрана*/
.overlay:target+.window {
    transform: translate(-50%, 0);
    top: 17%;
}
/*Внешний вид кнопки «Закрыть»*/
.close {
    top: -11px;
    right: -11px;
    width: 23px;
    height: 23px;
    position: absolute;
    padding: 0;
    border: 2px solid #ccd;
    border-radius: 15px;
    background-color: rgba(61, 61, 61, 0.81);
    box-shadow: 0 0 12px #010;
    text-align: center;
    text-decoration: none;
    font: 18px sans-serif;
    font-weight: bold;
    transition: all ease .9s;
}
.close:before {
    color: rgba(254, 254, 254, 0.89);
    content: "X";
    text-shadow: 0 1px 3px #010;
    font-size: 14px;
}
/*Изменение характеристик при наведении на область */
.close:hover {
    background-color: rgba(253, 21, 0, 0.83);
    transform: rotate(360deg);    
}
/*Оформление главной кнопки*/
#button-lay {
  margin-left: 40%;
font-size: 33px;
  border-radius: 11px;
    background-color: rgba(63, 63, 63, 0.9);
    box-shadow: 0 3px 10px #010;
    text-align: center;
    text-decoration: none;
   background: #DCDCDC; 
    padding: 6px 17px; 
}
</style>