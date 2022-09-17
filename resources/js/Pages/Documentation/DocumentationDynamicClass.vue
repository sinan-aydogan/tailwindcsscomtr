<template>
  <p>
    Projelerinizde her zaman durağan stiller kullanmak istemeyebilirsiniz, örneğin ekran genişliğine göre değişen
    responsive bir tasarıma ihtiyaç duyduğunuzda class'larınızın dinamik olarak görünümüzü değiştirmesi gerekir.
    Tailwind CSS ve VueJS'in gücü ile projeleriniz dinamik bir görünüme kavuşacaktır. Tailwind CSS ile <b><i>Pseudo-classes</i></b>
    ve <b><i>CSS Media Queries</i></b> yapılarını komponentlerimizde bolca kullandık.
  </p>
  <pre v-highlightjs class="my-4"><code class="javascript"
                                        v-text="'<div class=\'hidden sm:block\'></div>'"></code></pre>
  <p>
    Örneğinde ilgili <b>div</b> küçük ekranlarda gizli iken tablet ve sonraki genişlikte ekranlarda görünür olacaktır.
  </p>
  <pre v-highlightjs class="my-4">
    <code class="javascript"
          v-text="'<button class=\'p-2 bg-sky-500 hover:bg-sky-400 active:bg-amber-500 transition\'></button>'"/>
  </pre>
  <p>
    Örneğinde ilgili <b>button</b> üzerine geldiğinde ayrı, tıklandığında ayrı bir tarz ortaya çıkacaktır.
  </p>

  <p class="mt-4">
    VueJS kullanıyorsanız bu dinamik gösterimi bir tık daha öteye götürebilirsiniz.
  </p>
  <pre v-highlightjs class="my-4">
    <code class="javascript"
          v-text="'<template>\n' +
           '    <div \n' +
            '        class=\'flex border p-2\'\n' +
            '        :class={\n' +
             '            \'bg-green-500\': status\n' +
             '            \'bg-red-500\': !status\n' +
             '        }\n' +
             '    >\n' +
              '        {{ status ? \'Aktif\' : \'Pasif\' }}\n' +
            '    </div>\n' +
           '</template>' +
            '\n\n' +
             '<script setup>\n' +
              '    defineProps({\n' +
               '        status: Boolean\n' +
                '    })\n' +
                 '</script>'"/>
  </pre>

</template>