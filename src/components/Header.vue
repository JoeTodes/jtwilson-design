<template>
  <v-app-bar app>
    <router-link to="/" style="text-decoration:none">
      <v-toolbar-title class="headline black--text text-uppercase">
        <span>jtwilson</span>
        <span class="font-weight-light">.DESIGN</span>
      </v-toolbar-title>
    </router-link>

    <v-spacer></v-spacer>

    <v-toolbar-items class="hidden-sm-and-down">
      <v-menu
        open-on-hover
        offset-y
        v-for="item in navItems"
        :key="item.title"
        :disabled="item.dropdowns.length==0"
      >
        <template v-slot:activator="{ on }">
          <v-btn text :to="item.path" v-on="on">{{item.title}}</v-btn>
        </template>

        <v-list>
          <v-list-item v-for="(name, index) in item.dropdowns" :key="index">
            <v-btn text>{{name}}</v-btn>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-toolbar-items>
  </v-app-bar>
</template>

<script>
import smoothReflow from "vue-smooth-reflow";

export default {
  mixins: [smoothReflow],
  data() {
    return {
      navItems: [
        { title: "Projects", icon: null, path: "/projects", dropdowns: [] },
        {
          title: "Courses",
          icon: null,
          path: "/courses",
          dropdowns: ["CompSci 20", "Robotics 20", "Design Studies 20"]
        },
        { title: "Blog", icon: null, path: "/blog", dropdowns: [] },
        { title: "Contact", icon: null, path: "/contact", dropdowns: [] }
      ]
    };
  }
};
</script>