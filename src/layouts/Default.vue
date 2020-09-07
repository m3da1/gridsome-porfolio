<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      v-bind:color="color"
      v-bind:expand-on-hover="expandOnHover"
      v-bind:mini-variant="miniVariant"
      v-bind:right="right"
      v-bind:permanent="permanent"
      app
      fixed
      width="270px"
    >
      <v-list nav>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="pa-2 title">Mark Elorm Doh</v-list-item-title>
            <v-list-item-subtitle class="pa-2">Software Dev & Security++</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          v-bind:to="`#${item.title.toLowerCase().replace(/\s/g, '')}`"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <!-- <v-container> -->
      <slot />
      <!-- </v-container> -->
    </v-main>

    <v-footer app></v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      items: [
        { title: "About", icon: "mdi-account-box-outline" },
        { title: "Projects", icon: "mdi-apps" },
        { title: "Education", icon: "mdi-school-outline" },
        { title: "Contact", icon: "mdi-contacts-outline" },
      ],
      color: "#eeeeee",
      // color: "default",
      colors: ["primary", "blue", "success", "red", "teal"],
      right: false,
      permanent: true,
      miniVariant: false,
      expandOnHover: false,
      background: false,
    };
  },
  computed: {},
  methods: {
    toggleState() {
      this.miniVariant = !this.miniVariant;
    },
  },
};
</script>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
html {
  scroll-behavior: smooth;
}
</style>
