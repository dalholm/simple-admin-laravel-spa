<template>
  <!-- Sidebar -->
  <ul class="navbar-nav sidebar sidebar-dark accordion" id="accordionSidebar">

    <!-- Sidebar - Brand -->
    <router-link :to="{ name: user ? 'home' : '' }" class="sidebar-brand d-flex align-items-center justify-content-center" >
      <div class="sidebar-brand-icon rotate-n-15">
        <fa icon="beer"/>
      </div>
      <div class="sidebar-brand-text mx-3">
        {{ appName }}
      </div>
    </router-link>
    <locale-dropdown></locale-dropdown>

    <!-- Divider -->
    <hr class="sidebar-divider my-0">

    <!-- Nav Item - Dashboard -->
    <li class="nav-item active">
      <router-link class="nav-link" :to="{ name: user ? 'home' : '' }">
        <fa icon="home"/>
        <span>{{ $t('home')}}</span>
      </router-link>
    </li>

    <!-- Divider -->
    <hr class="sidebar-divider">

    <!-- Heading -->
    <div class="sidebar-heading">
      {{ $t('system') }}
    </div>

    <!-- Nav Item - Pages Collapse Menu -->
    <li class="nav-item">
      <a class="nav-link collapsed" href="#" data-toggle="collapse" data-target="#collapsePages" aria-expanded="true" aria-controls="collapsePages">
        <fa icon="cog"/>
        <span>{{ $t('settings') }}</span>
      </a>
      <div id="collapsePages" class="collapse" aria-labelledby="headingPages" data-parent="#accordionSidebar">
        <div class="bg-white py-2 collapse-inner rounded">
          <h6 class="collapse-header">{{ $t('settings') }}:</h6>
          <router-link class="collapse-item" :to="{ name: 'settings.profile' }">
            {{ $t('settings') }}
          </router-link>
        </div>
      </div>
    </li>
    <!-- Sidebar Toggler (Sidebar) -->
    <div class="text-center d-none d-md-inline">
      <button class="rounded-circle border-0" id="sidebarToggle" @click="toggleSidebar"></button>
    </div>

  </ul>
  <!-- End of Sidebar -->
</template>

<script>
import { mapGetters } from 'vuex'
import LocaleDropdown from './LocaleDropdown'

export default {
  components: {
    LocaleDropdown
  },

  data: () => ({
    appName: window.config.appName,
    windowWidth: 0,
    windowHeight: 0,
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
