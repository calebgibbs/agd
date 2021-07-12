<template>
  <div class="nav">
    <div class="logo">
      <router-link to="/">
        <img src="../assets/images/logos/logo.png" alt="logo" width="75px" />
      </router-link>
    </div>
    <div class="mobile">
      <button @click="toggleMenu">
        <img src="../assets/images/icons/menu.svg" alt="menu icon" />
      </button>
    </div>
    <div class="links" :class="{ show: menuOpen }">
      <ul>
        <li>
          <router-link @click.native="closeMenu" to="/">Home</router-link>
        </li>
        <li>
          <router-link @click.native="closeMenu" to="/services"
            >Services</router-link
          >
        </li>
        <li>
          <router-link @click.native="closeMenu" to="/photos"
            >Photos</router-link
          >
        </li>
        <li>
          <router-link @click.native="closeMenu" to="/contact"
            >Contact</router-link
          >
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
      console.log(this.menuOpen);
    },
    closeMenu() {
      this.menuOpen = false;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/styles/colors";
@import "../assets/styles/mediaqueries";

.nav {
  padding: 0.5em;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 3px solid $yellow;
}

.mobile {
  display: none;
}

ul {
  padding: 0;
  margin: 0;
}

li {
  display: inline-block;
  list-style-type: none;
  font-size: 1.3em;
  margin: 0 0.7em;
}

a {
  text-decoration: none;
  color: inherit;
  transition: color 0.1s ease-in-out;
  &:hover {
    color: $yellow;
  }
}

@mixin mobile-menu {
  .nav {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 2;
  }
  .logo {
    img {
      width: 3em;
    }
  }

  .show {
    display: block !important;
  }

  .links {
    display: none;
    grid-row: 2;
    grid-column: span 2;
    ul {
      width: 100%;
      margin-top: 1em;
      li {
        display: block;
        padding: 0.4em;
        text-align: center;
        border-top: 1px solid $yellow;
      }
    }
  }

  .mobile {
    display: block;
    float: right;
    margin-right: 0;
    button {
      outline: 0;
      background: none;
      border: none;
      float: right;
      padding: 0.3em;
    }
  }
}

@include mobile-portait {
  @include mobile-menu();
}

@include mobile-landscape {
  @include mobile-menu();
}
</style>
