<template>
  <!-- Page Wrapper -->
  <div id="wrapper">

    <sidebar v-if="user"/>
    <!-- Content Wrapper -->
    <div id="content-wrapper" class="d-flex flex-column">

      <!-- Main Content -->
      <div id="content">

        <navbar/>

        <!-- Begin Page Content -->
        <div class="container-fluid">
          <child/>
        </div>
      </div>

      <!-- Footer -->
      <footer class="sticky-footer bg-white">
        <div class="container my-auto">
          <div class="copyright text-center my-auto">
            <span>Copyright &copy;</span>
          </div>
        </div>
      </footer>
      <!-- End of Footer -->

    </div>
  </div>
</template>

<script>
import Navbar from '~/components/Navbar'
import Sidebar from '~/components/Sidebar'
import { mapGetters } from 'vuex'

export default {
  name: 'MainLayout',

  components: {
    Sidebar,
    Navbar
  },
    computed: mapGetters({
        user: 'auth/user'
    }),
  methods: {
    toggleSidebar() {
      var body = document.getElementsByTagName('body')[0];
      body.classList.toggle("sidebar-toggled");

      var sidebarElement = document.getElementsByClassName('sidebar')[0];
      sidebarElement.classList.toggle("toggled");
    }
  }
}
</script>
