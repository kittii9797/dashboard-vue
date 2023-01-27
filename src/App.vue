<template>
  <Header/>
  <MainBody/>
  <FooterMain/>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.min.js';
import Header from './components/Header.vue';
import FooterMain from './components/FooterMain.vue';
import MainBody from './components/MainBody.vue';

export default {
	name: 'App',
	components: {
		Header,
		FooterMain,
		MainBody
	}
};
</script>


