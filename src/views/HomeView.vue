<script setup>
import Contact from "@/components/Contact.vue";
import Footer from "@/components/Footer.vue";
import Header from "@/components/Header.vue";
import Intro from "@/components/Intro.vue";
import Port from "@/components/Port.vue";
import Site from "@/components/Site.vue";
import Skill from "@/components/Skill.vue";
import Skip from "@/components/Skip.vue";

</script>

<template>
  <Skip />
  <Header />
  <main id="main" role="main">
    <Intro />
    <Skill />
    <Site />
    <Port />
    <Contact />
  </main>
  <Footer />
  
  
</template>
