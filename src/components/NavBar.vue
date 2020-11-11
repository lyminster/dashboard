<template>
  <div class="div">
    <v-app-bar app flat>
      <v-toolbar-title class="text-uppercase grey--text text--darken-2"
        >PT GOOD LOOK</v-toolbar-title
      >
      <v-spacer></v-spacer>

      <v-btn text color="grey darken-2">
        <span class="text-upercase">Logout</span>
        <v-icon right>mdi-logout-variant</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer
      app
      v-model="drawer"
      :mini-variant.sync="mini"
      permanent
      class="grey darken-3"
    >
      <v-list-item class="px-2" @click.stop="mini = !mini">
        <v-list-item-avatar>
          <v-img src="https://randomuser.me/api/portraits/men/85.jpg"></v-img>
        </v-list-item-avatar>

        <v-list-item-title class="white--text">John Leider</v-list-item-title>

        <v-btn icon>
          <v-icon class="white--text">mdi-chevron-left</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item v-for="item in items" :key="item.title" link :to="item.href">
          <v-list-item-icon>
            <v-icon class="white--text">{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title class="white--text">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      items: [
        { title: "Dashboard", href:"/", icon: "mdi-home-city" },
        { title: "About Us",href:"/about", icon: "mdi-account" },
        { title: "Transaksi", href:"/transaction" ,icon: "mdi-account-group-outline" },
        { title: "Stok", href:"/transaction" ,icon: "mdi-account-group-outline" },
        { title: "Produk", href:"/transaction" ,icon: "mdi-account-group-outline" },
        { title: "History", href:"/transaction" ,icon: "mdi-account-group-outline" },
        { title: "MyAccount", href:"/transaction" ,icon: "mdi-account-group-outline" },
        { title: "Settings", href:"/transaction" ,icon: "mdi-cogs" },
      ],
      mini: false,
    };
  },
};
</script>

<style>
</style>