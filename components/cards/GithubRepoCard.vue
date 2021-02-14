<template>
  <div class="box">
    <article class="media">
      <div class="media-content">
        <div class="card-title card-header-title is-paddingless"
             v-text="$props.title"/>
        <div class="content" style="text-align: center;">
          <div v-if="!$data.ghRateLimit">
            <div style="align-items: start" v-for="repo in $data.githubRepos" :key="repo.id" v-if="!repo.fork">

              <div class="spacing"></div>
              <fa :icon="fab()[iconName(repo.language)]" :style="{ color: `${languageColor(repo.language)}` }"/>
              <a target="_blank"
                 class="link subtitle is-6"
                 :href="repo.html_url">
                <strong style="color: #9b8dc1">{{repo.name}}</strong>
                <br/><p class="title is-7" style="color: #8884c4">{{ repo.description }}</p>
              </a>
            </div>
          </div>
          <div v-else style="overflow: hidden">
            <p class="title">Rate limited :/</p>
          </div>
        </div>
      </div>
    </article>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'nuxt-property-decorator';
import { fab } from '@fortawesome/free-brands-svg-icons'

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
      ghRateLimit: false,
      languageColors: {
        java: "#ffba00",
        vue: "#7CBF98"
      }
    }
  }

  fab() {
    return fab;
  }

  iconName(languageName: string): string {
    if (!languageName) return "faGithub";
    let iconName: string = "fa";
    switch (languageName.toLowerCase()) {
      case "java":
        iconName += "Java";
        break;
      case "vue":
        iconName += "Vuejs";
        break;
      default:
        iconName += "github";
        break
    }
    return iconName;
  }

  languageColor(languageName: string): string {
    let iconColor: string = "pink";
    if (!languageName) return iconColor;
    switch (languageName.toLowerCase()) {
      case "java":
        iconColor = "#DE6666";
        break;
      case "vue":
        iconColor = "#759E72";
        break;
    }
    return iconColor;
  }

  async fetch() {
    const rateLimit = await this.$axios.$get("https://api.github.com/rate_limit");
    if (rateLimit.rate.remaining === 0) {
      this.$data.ghRateLimit = true;
      return;
    }
    this.githubRepos = await this.$axios.$get(`https://api.github.com/users/${this.githubName}/repos`);
  }
}
</script>

<style scoped>

</style>
