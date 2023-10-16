<template>
  <q-page class="">
    <div class="q-pa-none">
      <q-carousel
        arrows
        animated
        infinite
        v-model="slide"
        height="400px"
        :autoplay="1000"
      >
        <q-carousel-slide
          v-for="(slide, i) in itemsCarousel" :key="i + 'slide'"
          :name="slide.name"
          :img-src="slide.url"
        >
          <div class="absolute-bottom custom-caption">
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
        class="q-mt-md"
      >
        <div
          v-for="(item, index) in itemsRef"
          :key="index"
          class="caption row q-mt-md"
        >
          <div class="q-pa-md items-start q-gutter-md col">
            <q-card class="my-card" flat bordered>
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" />

              <q-card-section>
                <div class="text-overline text-orange-9">Overline</div>
                <div class="text-h5 q-mt-sm q-mb-xs">Title</div>
                <div class="text-caption text-grey">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                  do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </div>
              </q-card-section>

              <q-card-actions>
                <q-btn flat color="primary" label="Share" />
                <q-btn flat color="secondary" label="Book" />

                <q-space />

                <q-btn
                  color="grey"
                  round
                  flat
                  dense
                  :icon="expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
                  @click="expanded = !expanded"
                />
              </q-card-actions>

              <q-slide-transition>
                <div v-show="expanded">
                  <q-separator />
                  <q-card-section class="text-subtitle2">
                    {{ lorem }}
                  </q-card-section>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
          <div class="q-pa-md items-start q-gutter-md col">
            <q-card class="my-card" flat bordered>
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" />

              <q-card-section>
                <div class="text-overline text-orange-9">Overline</div>
                <div class="text-h5 q-mt-sm q-mb-xs">Title</div>
                <div class="text-caption text-grey">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                  do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </div>
              </q-card-section>

              <q-card-actions>
                <q-btn flat color="primary" label="Share" />
                <q-btn flat color="secondary" label="Book" />

                <q-space />

                <q-btn
                  color="grey"
                  round
                  flat
                  dense
                  :icon="expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
                  @click="expanded = !expanded"
                />
              </q-card-actions>

              <q-slide-transition>
                <div v-show="expanded">
                  <q-separator />
                  <q-card-section class="text-subtitle2">

                  </q-card-section>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
          <div class="q-pa-md items-start q-gutter-md col">
            <q-card class="my-card" flat bordered>
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" />

              <q-card-section>
                <div class="text-overline text-orange-9">Overline</div>
                <div class="text-h5 q-mt-sm q-mb-xs">Title</div>
                <div class="text-caption text-grey">
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed
                  do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                </div>
              </q-card-section>

              <q-card-actions>
                <q-btn flat color="primary" label="Share" />
                <q-btn flat color="secondary" label="Book" />

                <q-space />

                <q-btn
                  color="grey"
                  round
                  flat
                  dense
                  :icon="expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
                  @click="expanded = !expanded"
                />
              </q-card-actions>

              <q-slide-transition>
                <div v-show="expanded">
                  <q-separator />
                  <q-card-section class="text-subtitle2">

                  </q-card-section>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
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
    const itemsRef = ref([{}, {}, {}, {}, {}, {}, {}]);
    const itemsId = ref([{}, {}, {}, {}, {}, {}, {}]);
    const itemsCarousel = ref([
      {
        id: 1,
        name: 1,
        url: "https://cdn.quasar.dev/img/mountains.jpg",
        title: "First stop 1",
        subtitle: "Mountains 1",
      },
      {
        id: 2,
        name: 2,
        url: "https://cdn.quasar.dev/img/parallax1.jpg",
        title: "First stop 3",
        subtitle: "Mountains 3",
      },
      {
        id: 3,
        name: 3,
        url: "https://cdn.quasar.dev/img/parallax2.jpg",
        title: "First stop 4",
        subtitle: "Mountains 4",
      },
    ]);
    const scrollTargetRef = ref(null);
    const slide = ref(1);

    function onLoadRef(index, done) {
      setTimeout(() => {
        itemsRef.value.push({}, {}, {}, {}, {}, {}, {});
        done();
      }, 2000);
    }
    function onLoadId(index, done) {
      setTimeout(() => {
        itemsId.value.push({}, {}, {}, {}, {}, {}, {});
        done();
      }, 2000);
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
