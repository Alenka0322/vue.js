<template>
  <v-app id="inspire">
    <v-navigation-drawer   v-model="drawer" app>
    
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            INFORMATION
          </v-list-item-title>
          <v-list-item-subtitle>
            All that is needed
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list
        dense
        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          link
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

    <v-app-bar
      app
      color="primari"
      dark
      src="graz-g69b2ef0cb_1920.jpg"
      prominent
    >
      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(55,236,186,.1), rgba(25,32,72,.2)"
         
        ></v-img>
      </template>

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-app-bar-title>Lorem ips</v-app-bar-title>

      <v-spacer></v-spacer>

        <v-text-field
        @focus="searchClosed = false"
        @blur="searchClosed = true"
        v-model="search"
            placeholder="Search"
            prepend-inner-icon="mdi-magnify"
            class="Lorem-ips mt-1 "
            :class="{ 'closed' : searchClosed && !search }"
           
            filled
            dense
            clearable
          ></v-text-field>
    

     
    </v-app-bar>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null,
     items: [
          { title: 'Block', icon: 'mdi-view-dashboard', to:'/' },
          { title: 'Sign up', icon: 'mdi-account-circle', to:'/about' },
        ],
        search: null,
        searchClosed: true,
  
    }),
  }
</script>


<style lang="sass">
.v-input.Lorem-ips
  transition: max-width 0.3s
.v-input__slot
  cursor: pointer !important
  &:before, &:after
  border-color: transparent !important
.v-input.closed
  max-width: 45px
  .v-input__slot
    background: transparent imo !important
</style>