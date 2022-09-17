<template>
  Site genelinde <b><i>Montserrat</i></b> fontunu kullanıyoruz fakat komponent kodlarını kendi sitelerinizde taşıdığınızda yazılar kendi projenizdeki <i><b>tailwind.config.js</b></i> içinde tanımladığınız fontlar ile gösterilecektir.
  Eğer projenizdeki font ailesini değiştirmek istiyorsanız, <i><b>tailwind.config.js</b></i> içinde aşağıdaki gibi düzenlemeler yapabilirsiniz.
  <pre v-highlightjs class="mt-4"><code class="javascript">// tailwind.config.js
const defaultTheme = require('tailwindcss/defaultTheme')

module.exports = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['Montserrat', ...defaultTheme.fontFamily.sans],
      },
    },
  },
  // ...
}</code></pre>
</template>