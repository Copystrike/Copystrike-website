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
    return `<a href='${link}' target="_blank">${title}</a>`;
  }

}
</script>

//https://api.github.com/users/copystrike/repos

<style lang="css">

#middle-box {
  width: 1px;
}

</style>
