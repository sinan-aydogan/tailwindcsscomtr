<template>
  <p>Stiller arası geçilerin keskin dönüşümler olması yerine belirli bir zaman dilimi içinde kademeli geçmesini sağlayabilirsiniz. Mesela bir öğenin boyutunun 4rem den 8rem'e geçini 4-5-6-7-8 gibi akıcı bir şekilde sanki genişliyormuş hissettirecek şekilde gerçekleştirebilirsiniz.
    Sihirli kelime peki nedir ? <b><i>transition</i></b> ve <b><i>transition-all</i></b>. İkisi çok aynı görünse bile farklı özelliklere geçiş efekti verilmesini sağlıyorlar.
  </p>
  <table class="mt-4">
    <thead>
    <tr class=" font-semibold border-b">
      <td width="150">Class</td>
      <td>Etkilediği Özellik</td>
    </tr>
    </thead>
    <tbody>
    <tr class="h-4"></tr>
    <tr>
      <td class="px-4 py-2 bg-slate-100 rounded-l-lg font-semibold text-cyan-500">transition-none</td>
      <td class="px-4 py-2 bg-slate-100 rounded-r-lg">transition-property: none;</td>
    </tr>
    <tr class="h-4"></tr>
    <tr>
      <td class="px-4 py-2 bg-slate-100 rounded-l-lg font-semibold text-cyan-500">transition-all</td>
      <td class="px-4 py-2 bg-slate-100 rounded-r-lg">
        transition-property: all;<br><br>
        transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);<br><br>
        transition-duration: 150ms;<br></td>
    </tr>
    <tr class="h-4"></tr>
    <tr>
      <td class="px-4 py-2 bg-slate-100 rounded-l-lg font-semibold text-cyan-500">transition</td>
      <td class="px-4 py-2 bg-slate-100 rounded-r-lg">transition-property: color, background-color, border-color, text-decoration-color, fill, stroke, opacity, box-shadow, transform, filter, backdrop-filter;<br><br>
        transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);<br><br>
        transition-duration: 150ms;<br></td>
    </tr>
    </tbody>
  </table>
</template>