<script setup>
import GuestLayout from "@/Layouts/GuestLayout.vue"

const componentsList = [
  {
    id: 'layout',
    label: 'Yerleşimler',
    detail: 'İçeriklerinizin genel düzenini sağlayacağız ve genelde Main.vue gibi layout dosyalarınızda kullabileceğiniz tasarımlar.',
    components: [
      {
        id: 'layout-stacked',
        label: 'Tam Ekran Yerleşim',
      },
      {
        id: 'layout-sidebar',
        label: 'Yandan Menülü Yerleşim',
      },
      {
        id: 'layout-nested',
        label: 'İç İçe Yandan Menülü Yerleşim',
      },
      {
        id: 'layout-multicolumn',
        label: 'Çok Sütünlü Yerleşim',
      },
      {
        id: 'element-container',
        label: 'İçerik Alanları'
      },
      {
        id: 'element-panel',
        label: 'Paneller'
      },
      {
        id: 'element-modal',
        label: 'Açılan İçerik Penceleri'
      },
      {
        id: 'element-sidebar',
        label: 'Yandan Açılır Alanlar'
      }
    ]
  },
  {
    id: 'element',
    label: 'Temel Bileşenler',
    detail: 'İçerik oluşturmada kullanılacak temel düğme, avatar, select input ve benzeleri gibi bileşenler.',
    components: [
      {
        id: 'element-avatar',
        label: 'Avatarlar'
      },
      {
        id: 'element-dropdown',
        label: 'Açılır Menüler'
      },
      {
        id: 'element-badge',
        label: 'Etiketler'
      },
      {
        id: 'element-button',
        label: 'Düğmeler'
      },
      {
        id: 'element-list',
        label: 'Listeler'
      },
      {
        id: 'element-divider',
        label: 'Ayırıcılar'
      }
    ]
  },
  {
    id: 'navigation',
    label: 'Navigasyon',
    detail: 'İçerikle ilgili bilgi veren ve yönlendirme yapan komponentler.',
    components: [
      {
        id: 'heading-page',
        label: 'Sayfa Başlıkları'
      },
      {
        id: 'heading-card',
        label: 'İçerik Kartı Başlıkları'
      },
      {
        id: 'element-menu',
        label: 'Menüler'
      },
      {
        id: 'element-paginator',
        label: 'Sayfalandırmalar'
      },
      {
        id: 'element-step',
        label: 'Kademeli İçerikler'
      }
    ]
  },
  {
    id: 'feedback',
    label: 'Geribildirimler',
    detail: 'Kullanıcıları bilgilenme için kullanılan komponentler.',
    components: [
      {
        id: 'element-alert',
        label: 'Uyarı Kutuları'
      },
      {
        id: 'element-notification',
        label: 'Bildirimler'
      }
    ]
  },
  {
    id: 'data',
    label: 'Veri Görselleştirme',
    detail: 'Verinin görselleştirilmesi için kullanılan komponentler.',
    components: [
      {
        id: 'element-table',
        label: 'Tablolar'
      },
      {
        id: 'element-statistic',
        label: 'İstatistik Kutuları'
      },
      {
        id: 'element-list',
        label: 'Veri Listeleri'
      }
    ]
  }
]
</script>
<template>
  <guest-layout title="Tailwindcss.com.tr Komponentler">

    <!--CTA-->
    <div class="max-w-xl space-y-6">
      <p class="text-pink-500 font-semibold">
      Tailwind CSS in Öne Çıkan Yapıları
      </p>
      <h3 class="text-4xl font-extrabold">
        Tailwind CSS ile hazırlanmış <br> harika UI Komponentler
      </h3>
      <p class="text-slate-600">
        Projelerizde kullanmaya hazır. Bir çoğu dinamik ve VueJS ile desteklenmiş komponentler ile projelerinize elit bir hava katacaksınız.
      </p>
    </div>

    <!--Component Groups-->
    <div class="grid grid-cols-4 w-full border-slate-300 h-16 mt-8 mb-16 content-center text-center">
      <template v-for="i in componentsList">
        <a :href="'#'+i.id" v-text="i.label" class="border bg-slate-100 p-2 font-semibold text-sm cursor-pointer"></a>
      </template>
    </div>

    <!--Components Grid-->
    <div>
      <template v-for="i in componentsList">
        <div class="flex border-b last:border-0 py-8">
          <div :id="i.id" class="flex w-1/3 flex-col space-y-2 mb-8 pr-4">
            <h4 v-text="i.label" class="text-lg font-semibold"></h4>
            <span v-text="i.detail" class="text-xs text-slate-500"></span>
          </div>

          <!--Component Grids-->
          <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
            <template v-for="(j,index) in i.components">
              <div :id="j.id" class="flex flex-col">
                <h5 v-text="j.label" class="mb-2 text-sm font-semibold"></h5>
                <img :src="'https://picsum.photos/seed/'+Date.now()+index+'/400/200'">
                <span v-text="i.components.length + ' komponent'" class="text-xs mt-2 text-slate-500"></span>
              </div>
            </template>
          </div>
        </div>
      </template>
    </div>
  </guest-layout>
</template>