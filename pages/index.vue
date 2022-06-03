<template>
  <div>
    <div>
      <Header/>
    </div>
    <div v-if="catalog">
      <Shop/>
    </div>
    <div v-if="about">
      <Shop/>
    </div>
    <div v-if="contact">
      <Shop/>
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
    Checker() {
        
        
    }
  },
  methods: {
    clickCatalog(item) {
      this.catalog = true
      this.about = false
      this.contact = false
    }
  }
};
</script>