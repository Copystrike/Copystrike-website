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
</style>
