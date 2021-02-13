<template>
  <div class="box">
    <article class="media">
      <div class="media-content">
        <div class="card-title card-header-title is-paddingless"
             v-text="$props.title"/>
        <div class="content" style="text-align: center;">
          <div style="align-items: start" v-for="repo in $data.githubRepos" :key="repo.id" v-if="!repo.fork">
            <a target="_blank"
               class="link subtitle is-6"
               v-text="repo.name"
               :href="repo.html_url"
            ></a>
            <span class="" v-text="repo.language"></span>
          </div>
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

  githubRepos = [];

  data() {
    return {
      languageColors: {
        java: "#eb963d"
      }
    }
  }

  async fetch() {
    this.githubRepos = await this.$axios.$get(`https://api.github.com/users/${this.githubName}/repos`);
  }
}
</script>

<style scoped>

</style>
