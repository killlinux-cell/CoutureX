<template>
 <Navbar></Navbar>
 <Hero></Hero>
 <Presentation></Presentation>
 <Collection></Collection>
 <Contact></Contact>
 <Footer></Footer>
</template>


<script>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Presentation from './components/Presentation.vue';
import Collection from './components/Collection.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';

export default{
  name: 'App',
  components:{
    Navbar,
    Hero,
    Presentation,
    Collection,
    Contact,
    Footer,
  }
}
</script>


<style scoped>
@import './style.css';
</style>
