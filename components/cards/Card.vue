<template>
  <div class="box">
    <article class="media">
      <div class="media-content">
        <div class="card-header-title is-paddingless" v-text="$props.title"/>
        <div class="content">
          <p v-html="$props.description"/>
        </div>
      </div>
    </article>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator';

@Component({
  name: 'Card'
})
export default class Card extends Vue {

  @Prop()
  title?: String;

  @Prop()
  description?: String;
}
</script>

<style lang='css' scoped>

.box {
  box-shadow: 0 0.5em 1em -0.125em rgba(10, 10, 10, 0.4), 0 0 0 1px rgba(10, 10, 10, 0.02);
}
</style>
