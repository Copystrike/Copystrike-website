<template>
  <div class="columns is-mobile is-multiline is-8 my-5">
    <div id="container-1" class="column">
      <card title="Social medias" :description="$data.html" style="text-align: center"/>
    </div>
    <div id="container-2" class="column">
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
    this.socialLink("https://twitter.com/", "Nick_vn", "Twitter") + "<div class='spacing'></div>" +
    this.socialLink("https://github.com/", 'Copystrike', "Github") + "<div class='spacing'></div>" +
    this.socialLink("https://www.reddit.com/user/", "ReservedClass", "Reddit") + "<div class='spacing'></div>" +
    this.socialLink("https://discord.bio/p/", "Nick", "Discord") + "<div class='spacing'></div>" +
    this.socialLink("https://soundcloud.com/", "CopyNick", "SoundCloud")

  socialLink(link: string, username: string, title: string): string {
    return `
        <a id="${title.toLowerCase()}"
         class="link title is-5" href='${link}${username}'
         target="_blank">

         <strong>${title}</strong>
         <p class="title is-7" style="color: #8884c4">${username}</p>
         </a>`.trim();
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

#container-1 {
  padding-left: 12rem;
}

#container-2 {
  padding-right: 12rem;
}

.spacing {
  margin-bottom: 10px;
}
</style>
