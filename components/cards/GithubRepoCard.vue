<template>
  <div class="box">
    <article class="media">
      <div class="media-content">
        <div class="card-header-title is-paddingless" v-text="$props.title"/>
        <div class="content">
          <p>{{ this.$data.githubRepos }}</p>
        </div>
      </div>
    </article>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator';

@Component({
  name: 'GithubRepoCard'
})
export default class Card extends Vue {

  @Prop()
  title?: String;

  @Prop()
  githubName?: String;

  async data() {
    return {
      githubRepos
    }
  }

  async fetch() {
    this.$data.githubRepos = await this.$axios.$get(`https://api.github.com/users/${this.githubName}/repos`)
  }
}
</script>

<style scoped>

</style>
