<template>
  <!-- Topbar -->
  <nav class="navbar navbar-expand navbar-light bg-white topbar mb-4 static-top shadow">

    <!-- Sidebar Toggle (Topbar) -->
    <button id="sidebarToggleTop" class="btn btn-link d-md-none rounded-circle mr-3">
      <fa icon="bars" @click="toggleSidebar"/>
    </button>

    <!-- Topbar Navbar -->
    <ul class="navbar-nav ml-auto">
        <!-- Dropdown - Messages -->
        <div class="dropdown-menu dropdown-menu-right p-3 shadow animated--grow-in" aria-labelledby="searchDropdown">
          <form class="form-inline mr-auto w-100 navbar-search">
            <div class="input-group">
              <input type="text" class="form-control bg-light border-0 small" placeholder="Search for..." aria-label="Search" aria-describedby="basic-addon2">
              <div class="input-group-append">
                <button class="btn btn-primary" type="button">
                  <i class="fas fa-search fa-sm"></i>
                </button>
              </div>
            </div>
          </form>
        </div>
      </li>

      <div class="topbar-divider d-none d-sm-block"></div>

      <!-- Nav Item - User Information -->
      <li v-if="user" class="nav-item dropdown no-arrow">
        <a class="nav-link dropdown-toggle" href="#" id="userDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          <img :src="user.photo_url" class="img-profile rounded-circle">
          <span class="mr-2 d-none d-lg-inline text-gray-600 small ml-2">{{ user.name }}</span>
        </a>
        <!-- Dropdown - User Information -->
        <div class="dropdown-menu dropdown-menu-right shadow animated--grow-in" aria-labelledby="userDropdown">
          <!-- Dropdown - User Information -->
          <router-link :to="{ name: 'settings.profile' }" class="dropdown-item pl-3">
            <fa icon="cog" fixed-width/>
            {{ $t('settings') }}
          </router-link>

          <div class="dropdown-divider"/>

          <a href="#" class="dropdown-item pl-3" @click.prevent="logout">
            <fa icon="sign-out-alt" fixed-width/>
            {{ $t('logout') }}
          </a>
        </div>
      </li>
      <!-- Guest -->
      <template v-else>
        <li class="nav-item">
          <router-link :to="{ name: 'login' }" class="nav-link" active-class="active">
            {{ $t('login') }}
          </router-link>
        </li>
        <li class="nav-item">
          <router-link :to="{ name: 'register' }" class="nav-link" active-class="active">
            {{ $t('register') }}
          </router-link>
        </li>
      </template>

    </ul>

  </nav>
  <!-- End of Topbar -->


</template>

<script>
import { mapGetters } from 'vuex'
import LocaleDropdown from './LocaleDropdown'

export default {
  components: {
    LocaleDropdown
  },

  data: () => ({
    appName: window.config.appName
  }),

  computed: mapGetters({
    user: 'auth/user'
  }),

  methods: {
    async logout () {
      // Log out the user.
      await this.$store.dispatch('auth/logout')

      // Redirect to login.
      this.$router.push({ name: 'login' })
    },
    toggleSidebar() {
      this.$parent.toggleSidebar();
    }
  }
}
</script>

<style scoped>
.profile-photo {
  width: 2rem;
  height: 2rem;
  margin: -.375rem 0;
}
</style>
