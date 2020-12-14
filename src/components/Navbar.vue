<template>
  <b-navbar toggleable="lg" type="dark" class="navbar">
    <b-container>
        <b-navbar-brand href="#"><img class="brand-logo" src="@/assets/image/sap-concur.svg" /></b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#">PRODUCTS</b-nav-item>
            <b-nav-item href="#">SOLUTIONS</b-nav-item>
            <b-nav-item href="#">ABOUT US</b-nav-item>
            <b-nav-item href="#">RESOURCES</b-nav-item>
          </b-navbar-nav>
          <b-navbar-nav class="ml-auto">
            <div class="buttons">
              <b-button squared variant="outline-primary">TEST DRIVE</b-button>
              <b-button squared variant="outline-primary">LOGIN</b-button>
            </div>
            <div class="logo">
              <img src="@/assets/image/sap-logo.png" />
            </div>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
  </b-navbar>
</template>

<script>
export default {
  name: "Navbar"
}    
</script>

<style lang="sass" scoped>
  .navbar
    background-color: #000
    .brand-logo
      width: 165px
    #nav-collapse
      .nav-item a
        color: #fff
      .buttons button
        margin-right: 0.5rem
        &:first-child
          color: #f0ab00
          border-color: #f0ab00
          &:hover
            background-color: #f0ab00
            color: #fff
      .logo
        margin: auto
</style>