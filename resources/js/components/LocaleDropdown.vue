<template>

  <!-- Nav Item - Utilities Collapse Menu -->
  <li class="nav-item">
    <a class="nav-link collapsed" href="#" data-toggle="collapse" data-target="#collapseLocales" aria-expanded="true" aria-controls="collapseLocales">
      <i class="fas fa-fw fa-wrench"></i>
      <span>{{ locales[locale] }}</span>
    </a>
    <div id="collapseLocales" class="collapse" aria-labelledby="headingUtilities" data-parent="#accordionSidebar">
      <div class="bg-white py-2 collapse-inner rounded">
        <h6 class="collapse-header">{{ $t('choose_language') }}:</h6>
        <a v-for="(value, key) in locales" :key="key" class="collapse-item" href="#"
           @click.prevent="setLocale(key)">
          {{ value }}
        </a>
      </div>
    </div>
  </li>
</template>

<script>
import { mapGetters } from 'vuex'
import { loadMessages } from '~/plugins/i18n'

export default {
  computed: mapGetters({
    locale: 'lang/locale',
    locales: 'lang/locales'
  }),

  methods: {
    setLocale (locale) {
      if (this.$i18n.locale !== locale) {
        loadMessages(locale)

        this.$store.dispatch('lang/setLocale', { locale })
      }
    }
  }
}
</script>
