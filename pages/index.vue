<template>
  <div class="columns is-variable is-8 mx-5 my-5 is-centered is-multiline">
    <div class="column is-full">
      <card title="Social medias" :description="$data.html" style="text-align: center"/>
    </div>
    <div class="column">
      <github-repo-card title="My Github Repositories" github-name="Copystrike"></github-repo-card>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component } from "nuxt-property-decorator";

@Component({
  name: "index"
})
export default class index extends Vue {

  html = "" +
    this.socialLink("https://twitter.com/Nick130202", "Twitter") + "<br/>" +
    this.socialLink("https://github.com/Copystrike", "Github") + "<br/>" +
    this.socialLink("https://www.reddit.com/user/ReservedClass", "Reddit") + "<br/>" +
    this.socialLink("https://discord.bio/p/Nick", "Discord") + "<br/>" +
    this.socialLink("https://soundcloud.com/copynick", "SoundCloud") + "<br/>"

  socialLink(link: string, title: string): string {
    return `<a id="${title.toLowerCase()}" class="link" href='${link}' target="_blank">${title}</a>`;
  }

}
</script>

<style lang="css">

#middle-box {
  width: 1px;
}

.box {
  background-color: #7e6086;
  box-shadow: 0 0.5em 1em -0.125em rgba(10, 10, 10, 0.4), 0 0 0 1px rgba(10, 10, 10, 0.02);
}

.link {
  color: #9b8dc1;
}

.link:hover {
  color: #908bd0;
}

.card-header-title {
 color: #453D56;
}

.column {
  padding-left: 12rem !important;
  padding-right: 12rem !important;
}
</style>
