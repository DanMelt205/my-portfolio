<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      app
    >
      <v-list>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title class="title"> Daniel Melton </v-list-item-title>
            <v-list-item-subtitle> Software Engineer</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <v-footer :absolute="!fixed" padless app>
      <v-card class="flex" flat tile>
        <v-card-text class="py-2">
          <v-row justify="center" align-content="space-between">
            <div v-for="(icon, x) in icons" :key="x">
              <v-col cols="3">
                <v-btn :href="icon.url" :target="icon.target" dark icon>
                  <v-icon size="24px">
                    {{ icon.name }}
                  </v-icon>
                </v-btn>
              </v-col>
            </div>
          </v-row>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      fixed: false,
      items: [
        {
          icon: "mdi-home",
          title: "Home",
          to: "/",
        },
        {
          icon: "mdi-briefcase-outline",
          title: "Portfolio",
          to: "/portfolio",
        },
        {
          icon: "mdi-message-bulleted",
          title: "Contact",
          to: "/contact",
        },
      ],
      miniVariant: false,
      title: "Daniel Melton's Portfolio",
      icons: [
        {
          name: "mdi-linkedin",
          url: "https://www.linkedin.com/in/daniel-melton",
          target: "_blank",
        },
        {
          name: "mdi-github",
          url: "https://github.com/DanMelt205",
          target: "_blank",
        },
        {
          name: "mdi-file-pdf",
          url: "",
          target: "_blank",
        },
      ],
    };
  },
};
</script>
