<script setup>
import GuestLayout from "@/Layouts/GuestLayout.vue";

import AddingFont from './Documentation/DocumentationAddingFont.vue'
import CreateComponentAlpine from './Documentation/DocumentationCreateComponentAlpine.vue'
import CreateComponentVue from './Documentation/DocumentationCreateComponentVue.vue'
import DynamicClass from './Documentation/DocumentationDynamicClass.vue'
import Icons from './Documentation/DocumentationIcons.vue'
import Illustrations from './Documentation/DocumentationIllustrations.vue'
import Images from './Documentation/DocumentationImages.vue'
import InstallDependency from './Documentation/DocumentationInstallDependency.vue'
import Requirements from './Documentation/DocumentationRequirements.vue'
import Transitions from './Documentation/DocumentationTransitions.vue'


const menuItems = [
  {
    id: 'Starting',
    label: 'Başlarken',
    links: [
      {
        id: 'Requirements',
        label: 'Gereklilikler',
        component: Requirements
      },
      {
        id: 'AddingFont',
        label: 'Ek Yazı Tipi Ekleme',
        component: AddingFont
      },
    ]
  },
  {
    id: 'Dependencies',
    label: 'Bağımlılıklar',
    links: [
      {
        id: 'InstallDependency',
        label: 'Bağımlıkları Kurma',
        component: InstallDependency
      },
      {
        id: 'CreateComponentVue',
        label: 'Komponent Oluşturma (VueJS)',
        component: CreateComponentVue
      },
      // {
      //   id: 'CreateComponentAlpine',
      //   label: 'Komponent Oluşturma (AlpineJS)',
      //   component: CreateComponentAlpine
      // },
    ]
  },
  {
    id: 'Styles',
    label: 'Stiller',
    links: [
      {
        id: 'DynamicClass',
        label: 'Dinamik Class\'lar',
        component: DynamicClass
      },
      {
        id: 'Transitions',
        label: 'Geçiş Efektleri',
        component: Transitions
      }
    ]
  },
  {
    id: 'resources',
    label: 'Kaynaklar',
    links: [
      {
        id: 'Icons',
        label: 'İkonlar',
        component: Icons
      },
      {
        id: 'Images',
        label: 'Görseller',
        component: Images
      },
      // {
      //   id: 'Illustrations',
      //   label: 'Çizimler',
      //   component: Illustrations
      // }
    ]
  }
]
</script>

<template>
  <guest-layout title="Tailwindcss.com.tr Dökümantasyon">
    <div class="flex flex-col sm:flex-row space-y-8 sm:space-y-0 sm:space-x-24">
      <!--Links-->
      <div class="w-64 shrink-0">
        <template v-for="i in menuItems">
          <!--Header-->
          <div :id="i.id" class="flex flex-col">
            <a :href="'#'+i.id" v-text="i.label" class="font-semibold text-slate-700 cursor-pointer text-sm"></a>
          </div>

          <!--Sub Links-->
          <div class="my-4 text-slate-600 text-sm space-y-4 pl-4">
            <template v-for="j in i.links">
              <div :id="j.id" class="hover:ml-4 transition-all cursor-pointer">
                <a :href="'#'+j.id" v-text="j.label"></a>
              </div>
            </template>
          </div>
        </template>
      </div>

      <!--Content-->
      <div class="space-y-8">
        <template v-for="i in menuItems">
          <div class="border-b last:border-b-0">
            <h2 :id="i.id" v-text="i.label" class="text-xl font-bold text-slate-700 mb-2"></h2>

            <!--Sub Links-->
            <div class="text-sm">
              <template v-for="j in i.links">
                <div class="py-4">
                  <h3 v-text="j.label" class="font-semibold text-slate-700 mb-2"></h3>
                  <component :is="j.component"/>
                </div>
                <div class="flex justify-center items-center last:hidden text-slate-400 font-bold text-3xl leading-none">
                   .
                </div>
              </template>
            </div>
          </div>
        </template>
      </div>
    </div>
  </guest-layout>
</template>