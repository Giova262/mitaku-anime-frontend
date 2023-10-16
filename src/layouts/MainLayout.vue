<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-pink-4 text-grey-2 q-pl-md">
      <q-toolbar>
        Telfefono/Whatsapp :
        <q-btn round flat>
          <q-avatar size="20px">
            <img src="~assets/whatsapp.png" />
          </q-avatar>
        </q-btn>

        +54 911 2235 1904
        <q-btn round flat>
          <q-avatar size="20px">
            <img src="~assets/gmail.png" />
          </q-avatar>
        </q-btn>
        mitaku.anime@gmail.com

        <q-space />
        <q-btn round flat>
          <q-avatar size="20px">
            <img src="~assets/facebook.png" />
          </q-avatar>
        </q-btn>
        <q-btn round flat>
          <q-avatar size="20px">
            <img src="~assets/instagram.png" />
          </q-avatar>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <footer
      class="q-pa-lg section footer-classic context-dark bg-image"
      style="background: #2d3246"
    >
      <div class="container">
        <div class="row row-30">

          <div class="col col-xl-5">
            <div class="pr-xl-4">
              <a class="brand" href="index.html"
                ><img
                  class="brand-logo-light"
                  src="~assets/logo.jpg"
                  alt=""
                  width="49"
                  height="49"
              /></a>
              <p class="q-mt-sm q-pt-xs">
                We are an award-winning creative agency, dedicated to the best
                result in web design, promotion, business consulting, and
                marketing.
              </p>
              <!-- Rights-->
              <p class="rights">
                <span>© </span><span class="copyright-year">2023 </span
                ><span> </span><span>Mitaku Anime</span><span> - </span
                ><span>All Rights Reserved.</span>
              </p>
            </div>
          </div>

          <div class="col">
            <h5>Contacts</h5>
            <dl class="contact-list">
              <dt>Direccion:</dt>
              <dd>798 South Park Avenue, New York, USA</dd>
            </dl>
            <dl class="contact-list">
              <dt>Email:</dt>
              <dd><a href="mailto:#">compagny@email.com</a></dd>
            </dl>
            <dl class="contact-list">
              <dt>Telefonos:</dt>
              <dd>
                <a href="tel:#">1.555.652.258</a> <span>o </span>
                <a href="tel:#">1.55.652.268</a>
              </dd>
            </dl>
          </div>

        </div>
      </div>

      <!-- <div class="row no-gutters social-container">
        <div class="col">
          <a class="social-inner" href="#"
            ><span class="icon mdi mdi-facebook"></span><span>Facebook</span></a
          >
        </div>
        <div class="col">
          <a class="social-inner" href="#"
            ><span class="icon mdi mdi-instagram"></span
            ><span>Instagram</span></a
          >
        </div>
        <div class="col">
          <a class="social-inner" href="#"
            ><span class="icon mdi mdi-twitter"></span><span>Twitter</span></a
          >
        </div>
        <div class="col">
          <a class="social-inner" href="#"
            ><span class="icon mdi mdi-youtube-play"></span
            ><span>Youtube</span></a
          >
        </div>
      </div> -->

    </footer>
<!--
    <q-footer class="bg-grey-9 text-grey-2">
      <q-toolbar class="">
        <q-toolbar-title>Footer</q-toolbar-title>
      </q-toolbar>
    </q-footer> -->
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

const linksList = [
  {
    title: "Docs",
    caption: "quasar.dev",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "Github",
    caption: "github.com/quasarframework",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "Discord Chat Channel",
    caption: "chat.quasar.dev",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "Forum",
    caption: "forum.quasar.dev",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "Twitter",
    caption: "@quasarframework",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "Facebook",
    caption: "@QuasarFramework",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "Quasar Awesome",
    caption: "Community Quasar projects",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
