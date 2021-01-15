<template>
  <section>
    <navbar class="is-fullwidth"/>
    <Nuxt id="background"/>
  </section>
</template>

<style>
html {
  font-family: 'Source Sans Pro',
  -apple-system,
  BlinkMacSystemFont,
  'Segoe UI',
  Roboto,
  'Helvetica Neue',
  Arial,
  sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;

  height: 100%;
  width: 100%;

  background: hsla(197, 100%, 63%, 1);
  background: linear-gradient(90deg, hsla(197, 100%, 63%, 1) 0%, hsla(294, 100%, 55%, 1) 100%);
  background: -moz-linear-gradient(90deg, hsla(197, 100%, 63%, 1) 0%, hsla(294, 100%, 55%, 1) 100%);
  background: -webkit-linear-gradient(90deg, hsla(197, 100%, 63%, 1) 0%, hsla(294, 100%, 55%, 1) 100%);
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
