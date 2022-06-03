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
                    <p>{{ item }}</p>
                    <div v-for="(img, key) in imgs">
                        <div> </div>
                        <img v-if="key == item" id="ima" :src="img" />
                    </div>
                    
                    <blockquote>{{ value }}</blockquote>
                    <button v-on:click="addProduct(item)">Добавить в корзину</button>
                </div>
                <a class="close" title="Закрыть" href="/"></a>
        </div>
        <div id="shop">
            <div v-for="(value, item) in items">
                <button v-on:click="getProduct(item, value)">Подробнее</button>
                <div>
                    <div id="shop-item">
                        <img id="img" src="1.webp" :tittle="item" :alt="item"/>
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
                "Contact module with 1 contact element (Контактныймодульс 1 контактным элементом)": `Описание продукта:	ПРИВОД-/ИНДИКАТОРНЫЙ КОМПОНЕНТ КОНТАКТНЫЙ БЛОК С 1 КОНТАКТНЫМ ЭЛЕМЕНТОМ ПОДПРУЖИНЕННЫЙ ТЕРМИНАЛ, 1NC!!! Поэтапный продукт!!! SIRIUS ACT 3SU1 является преемником Предпочтительного типа преемника >>3SU1400-1AA10-3CA0<<;
                                                                                                    \n Жизненный цикл продукта (PLM)	PM490: Начало заключительного года поддержки; 
                                                                                                    \n Данные о ценах: Региональная ценовая группа / Ценовая группа штаб-квартиры	41J / 41J; 
                                                                                                    \n Прайс-лист:	Цена по запросу; 
                                                                                                    \n Цена клиента: Доплата за сырье - Нет; 
                                                                                                    \n Металлический фактор:	LBO-----; 
                                                                                                    \n Правила экспортного контроля:	ECCN: N / AL: N;
                                                                                                    \n Стандартное время выполнения ex-works:	10 дней;
                                                                                                    \n Вес нетто (кг):	0,009 кг;
                                                                                                    \n Размер упаковки:	92,00 x 105,00 x 52,00;
                                                                                                    \n Размер упаковки единица измерения:	ММ;
                                                                                                    \n Единица измерения количества:	1 шт.;
                                                                                                    \n Количество упаковки:	1;
                                                                                                    \n Дополнительная информация о продукте:
                                                                                                    \n EAN	4011209449824;
                                                                                                    \n UPC	754554654669;
                                                                                                    \n Код товара	85365080;
                                                                                                    \n LKZ_FDB/ CatalogID:	CC-IC10;
                                                                                                    \n Группа продуктов:	5832;
                                                                                                    \n Код группы:	R711;
                                                                                                    \n Страна происхождения: Китай;
                                                                                                    \n Соответствие с ограничениями вещества согласно директиве RoHS:	Начиная с: 01.07.2006;
                                                                                                    \n Класс продукта	C: продукты, изготовленные / произведенные на заказ, которые не могут быть повторно использованы или повторно использованы или возвращены в кредит;
                                                                                                    \n Обязательство по возврату WEEE (2012/19 / EU):	ДА.`,

                "Актуатор поворотного пере-ключателя с подсветкой 22мм":    `Описание: Преимущества устройств SIRIUS ACT: Современный дизайн: 4 варианта исполнения устройств для различных условий, легкость при выборе и монтаже, онлайн-конфигуратор с возможностью формирования заказа. быстрый монтаж одной рукой. Экстремальная надежность: стандартное исполнение для всех устройств — степень защиты IP69K, гибкие возможности коммуникации, поддержка интерфейсов: AS-Interface, IO-Link и PROFINET;
                                                                            Класс: Аксессуары для переключателей;
                                                                            Страна: Китай;
                                                                            Производитель: Schneider Electric;
                                                                            Ед.измерения: шт;
                                                                            Сертификат: RU C-DE.АЖ26.B03233;
                                                                            Наименование в прайсе производителя: АКТУАТОР ПОВОРОТНОГО ПЕРЕКЛЮЧАТЕЛЯ С ВОЗМОЖНОСТЬЮ ПОДСВЕТКИ, 22MM, КРУГЛ., ГЛЯНЦЕВЫЙ МЕТАЛЛ, КОРОТКАЯ ЧЁРНАЯ РУКОЯТКА С БЕЛОЙ ВСТАВКОЙ, 2 КОММУТАЦИОННЫХ ПОЛОЖЕНИЯ: O-I, С ФИКСАЦИЕЙ, УГОЛ ПОВОРОТА РУКОЯТКИ 90 ГРАД. : 10:30Ч./13:30Ч;
                                                                            Тип изделия: Актуатор;
                                                                            Диаметр отверстия, мм: 22.3;
                                                                            Тип управляющего элемента: Тумблер;
                                                                            Конструкция линзы: Прямоугольная.`,

                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод  24V UC красный с держателем ": `  Класс: Аксессуары для кнопочных постов и светосигнальной арматуры;
                                                                                                                                    Страна: Китай;
                                                                                                                                    Производитель: DEKraft;
                                                                                                                                    Ед.измерения: шт;
                                                                                                                                    Сертификат: RU C-DE.МЮ62.B00231;
                                                                                                                                    Диаметр отверстия, мм: 22;
                                                                                                                                    Степень защиты: IP66;
                                                                                                                                    Напряжение, В: 24.`,

                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC зеленый с держателем": "4кеонвкоклнл",
                "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC желтый с держателем": "тест5",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог": "тест6",
                "Контактор вспомогательный 4НО катушка управления 24В DC  или аналог": "тест7",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог": "тест8",
                "МОДУЛЬ БЛОК-КОНТАКТОВ, 2НО+2НЗ: 1НО, 1НЗ, 1НЗ, 1НО, Д. ВСПОМ. КОНТАКТОРОВ И КОНТАКТОРОВ ДЛЯ КОМ-МУТАЦИИ ЭЛЕКТРОДВИГА-ТЕЛЕЙ, ТИПОРАЗМЕР S00-S2, ВИНТОВЫЕ КЛЕММЫ": "тест9",
                "Реле времени": "тест10",
                "Клемма 4мм.кв 6.2мм серая": "тест11",
                "Клемма 4мм.кв 6.2мм синяя": "тест12",
                "Клемма 4мм.кв 6.2мм Ж/З –желто-зеленая": "тест13",
                "Coverterminal  или аналог": "тест14",
                "Through-type terminals (gray, 5.2mm)  илианалог": "тест15",
                "Jumperplug (5 divisions) или аналог": "тест16",
                "Таблички длинные 1 - 10, раз-мер ZB5": "тест17",
                "Таблички длинные 11 - 20, раз-мер ZB5": "тест18",
                "Таблички длинные 1 - 10, раз-мер ZB6": "тест19",
                "Блок питания 24 V/4 A": "тест20"
            },
    imgs: { "Contact module with 1 contact element (Контактныймодульс 1 контактным элементом)": "1.webp",
            "Актуатор поворотного пере-ключателя с подсветкой 22мм": "2.jpg",
            "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод  24V UC красный с держателем ": "3.jpg",
            "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC зеленый с держателем": "4кеонвкоклнл",
            "Комплектное устройство круг-лое индикатор с матовой линзой встроенный светодиод 24V UC желтый с держателем": "тест5",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог": "тест6",
                "Контактор вспомогательный 4НО катушка управления 24В DC  или аналог": "тест7",
                "Контактор вспомогательный 3НО+1НЗ AC 24V  или аналог": "тест8",
                "МОДУЛЬ БЛОК-КОНТАКТОВ, 2НО+2НЗ: 1НО, 1НЗ, 1НЗ, 1НО, Д. ВСПОМ. КОНТАКТОРОВ И КОНТАКТОРОВ ДЛЯ КОМ-МУТАЦИИ ЭЛЕКТРОДВИГА-ТЕЛЕЙ, ТИПОРАЗМЕР S00-S2, ВИНТОВЫЕ КЛЕММЫ": "тест9",
                "Реле времени": "тест10",
                "Клемма 4мм.кв 6.2мм серая": "тест11",
                "Клемма 4мм.кв 6.2мм синяя": "тест12",
                "Клемма 4мм.кв 6.2мм Ж/З –желто-зеленая": "тест13",
                "Coverterminal  или аналог": "тест14",
                "Through-type terminals (gray, 5.2mm)  илианалог": "тест15",
                "Jumperplug (5 divisions) или аналог": "тест16",
                "Таблички длинные 1 - 10, раз-мер ZB5": "тест17",
                "Таблички длинные 11 - 20, раз-мер ZB5": "тест18",
                "Таблички длинные 1 - 10, раз-мер ZB6": "тест19",
                "Блок питания 24 V/4 A": "тест20"
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
#img {
    width:170px;
    height:100px;
}
#ima {
    width:300px;
    height:300px;
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