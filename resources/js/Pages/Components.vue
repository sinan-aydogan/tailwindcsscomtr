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
        id: 'form',
        label: 'Form Bileşenleri',
        detail: 'Kullanıcıdan veri almak için kullanılan bileşenler.',
        components: [
            {
                id: 'search-input',
                label: 'Arama Kutuları'
            },
            {
                id: 'text-input',
                label: 'Text Inputlar'
            },
            {
                id: 'select-input',
                label: 'Açılır Listeler (Select)'
            },
            {
                id: 'Radio',
                label: 'Radyo Düğmeler'
            },
            {
                id: 'checkbox',
                label: 'Checkboxlar'
            },
            {
                id: 'range',
                label: 'Aralık Seçiciler'
            },
            {
                id: 'date-picker',
                label: 'Tarih Seçiciler'
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
      <h3 class="text-3xl md:text-4xl font-extrabold">
        Tailwind CSS ile hazırlanmış <br> harika UI Komponentler
      </h3>
      <p class="text-slate-600">
        Projelerizde kullanmaya hazır. Bir çoğu dinamik ve VueJS ile desteklenmiş komponentler ile projelerinize elit bir hava katacaksınız.
      </p>
    </div>

    <!--Component Groups-->
    <div class="grid grid-cols-2 lg:grid-cols-4 border-slate-300 h-16 mt-10 mb-4 content-center text-center">
      <template v-for="i in componentsList">
        <a :href="'#'+i.id" v-text="i.label" class="border bg-slate-100 p-2 font-semibold text-sm cursor-pointer"></a>
      </template>
    </div>

    <!--Components Grid-->
    <div>
      <template v-for="i in componentsList">
        <div class="flex flex-col lg:flex-row border-b last:border-0 py-8">
          <div :id="i.id" class="flex lg:w-1/3 flex-col space-y-2 mb-8 pr-4">
            <h4 v-text="i.label" class="text-lg font-semibold"></h4>
            <span v-text="i.detail" class="text-xs text-slate-500"></span>
          </div>

          <!--Component Grids-->
          <div class="grid sm:grid-cols-2 md:grid-cols-3 gap-4">
            <template v-for="(j,index) in i.components">
              <div :id="j.id" class="flex flex-col group transition-all active:scale-95 cursor-pointer">
                <h5 v-text="j.label" class="mb-2 text-sm font-semibold"></h5>
                <div class="relative">
                  <img :src="'https://picsum.photos/seed/'+Date.now()+index+'/400/200'" class="w-full object-cover group-hover:blur-[.1rem] transition-all duration-300" alt="Bileşen Ön İzlemesi">
                  <div class="hidden absolute group-hover:flex items-center justify-center top-0 left-0 w-full h-full text-white">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-20 h-20">
                      <path stroke-linecap="round" stroke-linejoin="round" d="M2.036 12.322a1.012 1.012 0 010-.639C3.423 7.51 7.36 4.5 12 4.5c4.638 0 8.573 3.007 9.963 7.178.07.207.07.431 0 .639C20.577 16.49 16.64 19.5 12 19.5c-4.638 0-8.573-3.007-9.963-7.178z" />
                      <path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                    </svg>

                  </div>
                </div>
                <span v-text="i.components.length + ' komponent'" class="text-xs text-right mt-2 text-slate-500"></span>
              </div>
            </template>
          </div>
        </div>
      </template>
    </div>
  </guest-layout>
</template>
