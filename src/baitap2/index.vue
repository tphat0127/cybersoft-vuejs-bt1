<template>
  <div>
      <Header />
      <Carousel />
      <div class="container">
        <div class="row">
            <WhatWeDo />
            <Contact />
        </div>
        
        <Listcard />
          
      </div>
      
      <Footer/>

  </div>
</template>

<script>
import Header from './header'
import Footer from './footer'
import Carousel from './carousel'
import Contact from './contact'
import WhatWeDo from './whatwedo'
import Listcard from './listcard'

export default {
    components: {
        Header,
        Footer,
        Carousel,
        WhatWeDo,
        Contact,
        Listcard,
    }
}
</script>

<style>
    
</style>