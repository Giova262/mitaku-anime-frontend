<template>
  <q-page class="">
    <div class="q-pa-none">
      <q-carousel
        arrows
        animated
        infinite
        v-model="slide"
        height="400px"
        :autoplay="5000"
      >
        <q-carousel-slide
          v-for="(slide, i) in itemsCarousel"
          :key="i + 'slide'"
          :name="slide.name"
          :img-src="'src/assets/' + slide.url"
        >
          <div
            v-if="slide.title || slide.subtitle"
            class="absolute-bottom custom-caption"
          >
            <div class="text-h2">{{ slide.title }}</div>
            <div class="text-subtitle1">{{ slide.subtitle }}</div>
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>

    <div
      ref="scrollTargetRef"
      class="q-px-md container q-my-md"
      style="height: 800px; overflow: auto; width: auto"
    >
      <q-infinite-scroll
        @load="onLoadRef"
        :offset="250"
        :scroll-target="scrollTargetRef"
        class="q-mt-md row"
      >
        <div
          v-for="(item, index) in itemsRef"
          :key="index"
          class="caption row q-mt-md col-3 q-pa-md"
        >
          <q-card class="my-card full-width" flat bordered>
            <q-img :src="'src/assets' + item.url" class="" />

            <q-card-section>
              <div class="text-overline text-orange-9">{{ item.overline }}</div>
              <div class="text-h5 q-mt-sm q-mb-xs">{{ item.title }}</div>
              <div class="text-caption text-grey">{{ item.desc }}</div>
            </q-card-section>
          </q-card>
        </div>

        <template v-slot:loading>
          <div class="row justify-center q-my-md">
            <q-spinner-dots color="primary" size="40px" />
          </div>
        </template>
      </q-infinite-scroll>
    </div>

    <q-separator style="height: 2px" />
  </q-page>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "IndexPage",
  setup() {
    const itemsRef = ref([
      {
        id: 1,
        url: "/0.jpg",
        overline: "Anime ",
        title: "YLEAFUN",
        desc: "Figure PVC Statue Cartoon Anime Girls Action Figure Model Collection Ornaments",
      },
      {
        id: 2,
        url: "/1.png",
        overline: "Anime ",
        title: "HUNTER X HUNTER",
        desc: "MIREN LO QUE SON ESTAS FIGURAS ULTRA CHIBIS 🥰🥰",
      },
      {
        id: 3,
        url: "/2.png",
        overline: "Anime ",
        title: "FIGURAS CHIBI DE JOJOS",
        desc: "Nos arriesgamos y trajimos figuras de jojos 😎💖",
      },
      {
        id: 4,
        url: "/3.png",
        overline: "Anime ",
        title: "JUJUTSU KAISEN",
        desc: "Después de todo lo que pasó en el anime y manga, no podía faltar JUJUTSU KAISEN 🥺🥺🥺",
      },
      {
        id: 5,
        url: "/4.png",
        overline: "Anime ",
        title: " KIMETSU ",
        desc: "AL FIN TRAJIMOS POSTERS DE KIMETSU 💥💥",
      },
      {
        id: 6,
        url: "/5.png",
        overline: "Anime ",
        title: "TOKYO REVENGERS",
        desc: "Llegaron más pósters... y no podían faltar de💥💥💥💥💥TOKYO REVENGERS 💥💥💥💥💥",
      },
      {
        id: 7,
        url: "/6.png",
        overline: "Anime ",
        title: "HAIKYUU",
        desc: "🔥🔥 Y QUE MEJOR FORMA DE FESTEJAR QUE TRAYENDO MAS FIGURAS DE HAIKYUU 🔥🔥",
      },
      {
        id: 8,
        url: "/7.png",
        overline: "Anime ",
        title: "ONE PIECE",
        desc: "Mide 27 CM e incluye caja",
      },
    ]);
    const itemsId = ref([{}, {}, {}, {}, {}, {}, {}]);
    const itemsCarousel = ref([
      {
        id: 1,
        name: 1,
        url: "s2.png",
        title: null,
        subtitle: null,
      },
      {
        id: 2,
        name: 2,
        url: "s3.jpeg",
        title: null,
        subtitle: null,
      },
      {
        id: 3,
        name: 3,
        url: "s1.jpg",
        title: "Mar del Plata",
        subtitle: null,
      },
      {
        id: 4,
        name: 4,
        url: "s5.jpg",
        title: "✨Anime- videojuegos - kpop✨",
        subtitle: null,
      },
    ]);
    const scrollTargetRef = ref(null);
    const slide = ref(1);

    function onLoadRef(index, done) {
      done();
      /*setTimeout(() => {
        itemsRef.value.push({}, {}, {}, {}, {}, {}, {});
        done();
      }, 2000);*/
    }
    function onLoadId(index, done) {
      done();
      /*setTimeout(() => {
        itemsId.value.push({}, {}, {}, {}, {}, {}, {});
        done();
      }, 2000);*/
    }
    return {
      itemsCarousel,
      itemsRef,
      itemsId,
      scrollTargetRef,
      slide,
      onLoadRef,
      onLoadId,
    };
  },
});
</script>
