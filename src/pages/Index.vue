<template>
  <div class="">
    <div class="col-md-4 col-xs-12 bg-grey-2">
      <div class="q-mb-md row justify-between">
        <q-tabs
          class=""
          active-color="secondary"
          align="left"
          :breakpoint="false"
          dense
          indicator-color="secondary"
          v-model="tabs.indexer">
          <q-tab
            :label="label"
            :name="index"
            v-for="(label,index) in tabs.labels"
            :key="index">
            <q-badge
              color="red"
              floating
              v-if="tabs.badges[index]">
              {{ tabs.badges[index] }}
            </q-badge>
          </q-tab>
        </q-tabs>
        <q-btn
          class=""
          dense
          round
          unelevated
          icon="menu"/>
      </div>

      <q-tab-panels
        class="bg-grey-2"
        animated
        v-model="tabs.indexer">
        <q-tab-panel :name="0">

            <q-card class="q-mb-md" flat>
              <q-carousel
                class="rounded-borders"
                v-model="carousel.indexer"
                animated
                autoplay
                height="230px"
                infinite
                navigation
                padding
                swipeable
                transition-prev="slide-right"
                transition-next="slide-left">
                <q-carousel-slide
                  class="column no-wrap flex-center"
                  :img-src="item"
                  :name="index"
                  v-for="(item,index) in carousel.items"
                  :key="index"/>
              </q-carousel>
            </q-card>
            <q-card class="q-mb-md" flat>
              <q-item>
                <q-item-section avatar>
                  <q-avatar>
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png" alt="avatar">
                  </q-avatar>
                </q-item-section>

                <q-item-section>
                  <q-item-label>Title</q-item-label>
                  <q-item-label caption>
                    Subhead
                  </q-item-label>
                </q-item-section>
              </q-item>

              <q-separator/>

              <q-card-section horizontal>
                <q-card-section>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit....
                </q-card-section>
                <q-separator vertical/>
                <q-card-section class="col-4">
                  <q-list>
                    <q-item clickable>
                      <q-item-section avatar>
                        <q-icon color="secondary" name="share"/>
                      </q-item-section>
                      <q-item-section>
                        <q-item-label>Share</q-item-label>
                      </q-item-section>
                    </q-item>

                    <q-item clickable>
                      <q-item-section avatar>
                        <q-icon color="teal" name="comment"/>
                      </q-item-section>

                      <q-item-section>
                        <q-item-label>Talk</q-item-label>
                      </q-item-section>
                    </q-item>

                    <q-item clickable>
                      <q-item-section avatar>
                        <q-icon color="red" name="favorite"/>
                      </q-item-section>

                      <q-item-section>
                        <q-item-label>Favorite</q-item-label>
                      </q-item-section>
                    </q-item>
                  </q-list>

                </q-card-section>
              </q-card-section>
            </q-card>
            <q-card class="q-mb-md" flat>
              <q-item>
                <q-item-section avatar>
                  <q-avatar>
                    <img src="https://cdn.quasar.dev/img/boy-avatar.png" alt="avatar">
                  </q-avatar>
                </q-item-section>

                <q-item-section>
                  <q-item-label>Title</q-item-label>
                  <q-item-label caption>
                    Subhead
                  </q-item-label>
                </q-item-section>
              </q-item>

              <q-separator/>

              <q-card-section horizontal>
                <q-card-section>
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                  Lorem ipsum dolor sit amet, consectetur adipiscing elit....
                </q-card-section>
                <q-separator vertical/>
                <q-card-section class="col-4">
                  <q-list>
                    <q-item clickable>
                      <q-item-section avatar>
                        <q-icon color="secondary" name="share"/>
                      </q-item-section>
                      <q-item-section>
                        <q-item-label>Share</q-item-label>
                      </q-item-section>
                    </q-item>

                    <q-item clickable>
                      <q-item-section avatar>
                        <q-icon color="teal" name="comment"/>
                      </q-item-section>

                      <q-item-section>
                        <q-item-label>Talk</q-item-label>
                      </q-item-section>
                    </q-item>

                    <q-item clickable>
                      <q-item-section avatar>
                        <q-icon color="red" name="favorite"/>
                      </q-item-section>

                      <q-item-section>
                        <q-item-label>Favorite</q-item-label>
                      </q-item-section>
                    </q-item>
                  </q-list>

                </q-card-section>
              </q-card-section>
            </q-card>
            <q-card class="q-mb-md" flat>
              <q-img src="https://cdn.quasar.dev/img/chicken-salad.jpg"/>
              <q-card-section>
                <q-btn
                  fab
                  color="primary"
                  icon="place"
                  class="absolute"
                  style="top: 0; right: 12px; transform: translateY(-50%);"/>

                <div class="row no-wrap items-center">
                  <div class="col text-h6 ellipsis">
                    Cafe Basilico
                  </div>
                  <div class="col-auto text-grey text-caption q-pt-md row no-wrap items-center">
                    <q-icon name="place"/>
                    250 ft
                  </div>
                </div>

                <q-rating :max="5" size="32px" model-value=""/>
              </q-card-section>

              <q-card-section class="q-pt-none">
                <div class="text-subtitle1">
                  $・Italian, Cafe
                </div>
                <div class="text-caption text-grey">
                  Small plates, salads & sandwiches in an intimate setting.
                </div>
              </q-card-section>

              <q-separator/>

              <q-card-actions>
                <q-btn flat round icon="event"/>
                <q-btn flat color="primary">
                  Reserve
                </q-btn>
              </q-card-actions>
            </q-card>
        </q-tab-panel>

        <q-tab-panel :name="1">
          <q-page class="flex flex-center">
            <img
              alt="Quasar logo"
              src="~assets/quasar-logo-vertical.svg"
              style="width: 200px; height: 200px">
          </q-page>
        </q-tab-panel>

        <q-tab-panel :name="2">
          <q-page class="flex flex-center">
            <img
              alt="Quasar logo"
              src="~assets/quasar-logo-vertical.svg"
              style="width: 200px; height: 200px">
          </q-page>
        </q-tab-panel>

        <q-tab-panel :name="3">
          <q-page class="flex flex-center">
            <img
              alt="Quasar logo"
              src="~assets/quasar-logo-vertical.svg"
              style="width: 200px; height: 200px">
          </q-page>
        </q-tab-panel>

        <q-tab-panel :name="4">
          <q-page class="flex flex-center">
            <img
              alt="Quasar logo"
              src="~assets/quasar-logo-vertical.svg"
              style="width: 200px; height: 200px">
          </q-page>
        </q-tab-panel>
      </q-tab-panels>


    </div>
  </div>

</template>

<script>
import {defineComponent, ref} from 'vue';

export default defineComponent({
  name: 'PageIndex',
  data() {
    return {
      tabs: {
        indexer: ref(0),
        labels: [
          "Sec A",
          "Sec B",
          "Sec C",
          "Sec D",
          "Sec E",
        ],
        badges: [
          null,
          '2',
          '99+',
          null,
          '13',
        ]
      },
      carousel: {
        indexer: ref(0),
        items: [
          "https://cdn.quasar.dev/img/mountains.jpg",
          "https://cdn.quasar.dev/img/parallax1.jpg",
          "https://cdn.quasar.dev/img/parallax2.jpg",
          "https://cdn.quasar.dev/img/quasar.jpg"
        ]
      }
    }
  }
})
</script>
