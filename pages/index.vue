<template>
  <div>
    <div>
      <Header v-on:mana="opa"/>
    </div>
    <div v-if="catalog">
      <Shop/>
    </div>
    <div v-if="about">
      <About/>
    </div>
    <div v-if="contact">
      <Contact/>
    </div>
    <div>
      <Footer/>
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
  },
  methods: {
    clickCatalog() {
      this.catalog = true
      this.about = false
      this.contact = false
    },
    clickAbout() {
      this.catalog = false
      this.about = true
      this.contact = false
    },
    clickContact() {
      this.catalog = false
      this.about = false
      this.contact = true
    },
    opa(catalog, about, contact) {
      this.catalog = catalog
      this.about = about
      this.contact = contact
      console.log(`mother eat`)
    }
  }
};
</script>