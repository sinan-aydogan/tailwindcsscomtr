<template>
  Dinamik komponentleri basit bir şekilde geliştirmek için VueJS'ten faydalanabilirsiniz.
  VueJS size hem verinizi yönetme imkanı verirken içeriğinizin stili üzerinde söz sahibi olma imkanıda sağlamaktadır.
  Tailwind CSS class'larını direk VueJS komponentleriniz <span v-text="'<template></template>'" class="font-semibold decoration-2 underline decoration-amber-500"></span> tag ları arasında kullanabilirsiniz veya <i>SASS</i> kullanarak komponentinizin <span v-text="'<style></style>'" class="font-semibold decoration-2 underline decoration-amber-500"></span> bloğu içinde de @apply ile custom class'larınızı tanımlayabilirsiniz.

  <pre v-highlightjs class="mt-4"><code class="javascript" v-text="'<template>\n' +
   '    <div class=\'relative bg-red-500 px-4 py-2\'>\n' +
    '        <span class=\'text-white font-semibold\'>Üye bilgisi silindi !</span>\n' +
     '        <span @click=\'toogleAlert\' class=\'absolute -top-2 -right-2 font-bold\'>x</span>\n' +
     '    </div>\n' +
   '</template>\n' +
    '\n' +
     '<script setup>\n' +
      '    import {ref} from \'vue\'\n' +
      '    const showAlert = ref(false)\n' +
      '    const toogleAlert = ()=>{\n' +
       '        showAlert.value = !showAlert.value\n' +
       '    }\n' +
      '</script>'"/></pre>
</template>