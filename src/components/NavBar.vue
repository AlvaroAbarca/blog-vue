<template>
<div>
  <b-navbar toggleable="lg" type="dark" variant="info" fixed="top">
    <b-container>
      <b-navbar-brand href="#">NavBar</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">Inicio</b-nav-item>
          <b-nav-item href="#">Posts</b-nav-item> <!-- disabled -->
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <!-- <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
          </b-nav-form> -->

          <b-nav-item-dropdown text="Lang" right>
            <b-dropdown-item href="#">EN</b-dropdown-item>
            <b-dropdown-item href="#">ES</b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown right>
            <!-- Using 'button-content' slot -->
            <template v-slot:button-content>
              <em>{{ user}} </em>
            </template>
            <b-dropdown-item href="#">Profile</b-dropdown-item>
            <b-dropdown-item href="#">Sign Out</b-dropdown-item>
          </b-nav-item-dropdown>
          
        </b-navbar-nav>
      </b-collapse>
    </b-container>
  </b-navbar>
</div>
</template>
<style lang="scss">

</style>
<script lang="ts">
import Vue from 'vue'
import { NavbarPlugin } from 'bootstrap-vue'
import { Component, Prop } from 'vue-property-decorator';
Vue.use(NavbarPlugin)

@Component({
  props: {
      user: String
  }
})
export default class NavBar extends Vue {
}
</script>