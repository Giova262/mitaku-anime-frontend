<template>
  <q-page class="">
    <div class="q-pa-none">
      <q-carousel
        arrows
        animated
        infinite
        v-model="slide"
        height="400px"
        :autoplay="12000"
      >
        <q-carousel-slide
          name="first"
          img-src="https://cdn.quasar.dev/img/mountains.jpg"
        >
          <div class="absolute-bottom custom-caption">
            <div class="text-h2">First stop</div>
            <div class="text-subtitle1">Mountains</div>
          </div>
        </q-carousel-slide>
        <q-carousel-slide
          name="second"
          img-src="https://cdn.quasar.dev/img/parallax1.jpg"
        >
          <div class="absolute-bottom custom-caption">
            <div class="text-h2">Second stop</div>
            <div class="text-subtitle1">Famous City</div>
          </div>
        </q-carousel-slide>
        <q-carousel-slide
          name="third"
          img-src="https://cdn.quasar.dev/img/parallax2.jpg"
        >
          <div class="absolute-bottom custom-caption">
            <div class="text-h2">Third stop</div>
            <div class="text-subtitle1">Famous Bridge</div>
          </div>
        </q-carousel-slide>
      </q-carousel>
    </div>

    <div
      ref="scrollTargetRef"
      class="q-px-md container q-my-md"
      style="height: 800px; overflow: auto; width: auto;"
    >
      <q-infinite-scroll
        @load="onLoadRef"
        :offset="250"
        :scroll-target="scrollTargetRef"
        class="q-mt-md"
      >
        <div v-for="(item, index) in itemsRef" :key="index" class="caption row q-mt-md">
          <div class="q-pa-md items-start q-gutter-md col ">
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
          <div class="q-pa-md items-start q-gutter-md col ">
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
          <div class="q-pa-md items-start q-gutter-md col ">
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
    const scrollTargetRef = ref(null);
    const items = ref([
      {
        id: 1,
        name: "Ruddy Jedrzej",
        email: "rjedrzej0@discuz.net",
        letter: "R",
      },
      {
        id: 2,
        name: "Mallorie Alessandrini",
        email: "malessandrini1@marketwatch.com",
        letter: "M",
      },
      {
        id: 3,
        name: "Elisabetta Wicklen",
        email: "ewicklen2@microsoft.com",
        letter: "E",
      },
      {
        id: 4,
        name: "Seka Fawdrey",
        email: "sfawdrey3@wired.com",
        letter: "S",
      },
      {
        id: 3,
        name: "Elisabetta Wicklen",
        email: "ewicklen2@microsoft.com",
        letter: "E",
      },
      {
        id: 4,
        name: "Seka Fawdrey",
        email: "sfawdrey3@wired.com",
        letter: "S",
      },
      {
        id: 4,
        name: "Seka Fawdrey",
        email: "sfawdrey3@wired.com",
        letter: "S",
      },
      {
        id: 3,
        name: "Elisabetta Wicklen",
        email: "ewicklen2@microsoft.com",
        letter: "E",
      },
      {
        id: 4,
        name: "Seka Fawdrey",
        email: "sfawdrey3@wired.com",
        letter: "S",
      },
    ]);

    return {
      itemsRef,
      itemsId,
      scrollTargetRef,

      onLoadRef(index, done) {
        setTimeout(() => {
          itemsRef.value.push({}, {}, {}, {}, {}, {}, {});
          done();
        }, 2000);
      },

      onLoadId(index, done) {
        setTimeout(() => {
          itemsId.value.push({}, {}, {}, {}, {}, {}, {});
          done();
        }, 2000);
      },
      items,
      slide: ref("first"),
      onLoad(index, done) {
        console.log("onloading");
        /*setTimeout(() => {
        console.log('alhgo')

          items.value.splice(0, 0, {}, {}, {}, {}, {}, {}, {})
          done()
        }, 2000)*/
      },
    };
  },
});
</script>
