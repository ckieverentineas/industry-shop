<!-- Please remove this file from your project -->
<template>
  <div id="main">
    <div id="nav">
      <img id="logo" src="favicon.ico"/>
      <div v-on:click="clickCatalog"> Каталог </div>
      <div v-on:click="clickAbout"> О нас </div>
      <div v-on:click="clickContact"> Контакты </div>
      <img v-on:click="clickCard" id="cart" src="cart.png"/>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      catalog: true,
      about: false,
      contact: false
    };
  },
  computed: {
    Checker() {
        this.$emit('mana', this.catalog, this.about, this.contact);
        console.log('children work')
    }
  },
  methods: {
    clickCatalog() {
      this.catalog = true
      this.about = false
      this.contact = false
      this.$emit('mana', this.catalog, this.about, this.contact);
      console.log('children work')
    },
    clickAbout() {
      this.catalog = false
      this.about = true
      this.contact = false
      this.$emit('mana', this.catalog, this.about, this.contact);
      console.log('children work')
    },
    clickContact() {
      this.catalog = false
      this.about = false
      this.contact = true
      this.$emit('mana', this.catalog, this.about, this.contact);
      console.log('children work')
    },
    clickCard() {
      this.$emit('manacard');
      console.log('card work')
      
    }
  }
};
</script>

<style scoped>
div { 
  width: 100%;
  margin-left: auto;
  margin-right: auto;
  display: flex;
  align-items: center;
  text-align: center;
  justify-content: center;
  vertical-align: middle;
}

#nav {
  /* nav/desktop */
  width: 100%;
  top: 0px;
  background: #d3eff0;
  display: inline-flex; 
}
#logo {
  /* logo */
  width: 100px;
  height: 50px;
}

#cart {
  /* Cart */
width: 26px;
height: 26px;
}
</style>