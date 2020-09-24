<template>
  <div id="app">
    <div class="wrapper">
      <b-navbar class="fixed-top" toggleable="lg">
        <b-navbar-brand to="/">
          <img id="nav-brand-img" :src="require('./assets/coffee-cup.svg')" />
        </b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item to="/">Home</b-nav-item>
            <b-nav-item to="/menu">Menu</b-nav-item>
            <b-nav-item to="/gift">Gift</b-nav-item>
            <b-nav-item to="/about">About</b-nav-item>
          </b-navbar-nav>

          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-button>I am a Button</b-button>
            <b-button href="#">I am a Link</b-button>
            <b-nav-item-dropdown right>
              <!-- Using 'button-content' slot -->
              <template v-slot:button-content>
                <em>User</em>
              </template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Sign Out</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <router-view />
    <footer>
      <b-container class="footer-container">
        <b-row align-h="center" align-v="center">
          <ul class="list-inline">
            <li class="list-inline-item">
              <a href="#">Privacy Policy</a>
            </li>
            <li class="list-inline-item">
              <a href="#">Terms of Use</a>
            </li>
            <li class="list-inline-item">
              <a href="#">Contact Us</a>
            </li>
            <li class="list-inline-item">
              <a href="#">Careers</a>
            </li>
          </ul>
        </b-row>
      </b-container>
    </footer>
  </div>
</template>

<style lang="scss">
#app {
  font-family: "Dosis", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav-brand-img {
  max-height: 40px;
  max-width: 40px;
}

.navbar {
  background-color: white;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.25), 0 4px 4px rgba(0, 0, 0, 0.15);
}

footer {
  background-color: #39210c;
  color: white;
  height: 100px;

  .footer-container {
    height: 100%;
    .row {
      height: 100%;
    }
  }

  li {
    margin: 0 20px;
  }
  a {
    color: white;
    &:hover {
      color: white;
    }
  }
}
</style>
