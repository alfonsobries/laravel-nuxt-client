<template>
  <layout-container>
    <layout-container col>
      <layout-navigation class="absolute w-full">
        <container class="flex">
          <nuxt-link 
            :to="{ name: authenticated ? 'home' : 'welcome' }"
            class="no-underline">
            <logo :alt="appName" />
          </nuxt-link>

          <ul class="ml-auto flex">
            <locale-dropdown class="mr-6" />
            <li 
              v-if="authenticated" 
              class="mr-6">
              <router-link :to="{ name: 'home' }">
                {{ $t('home') }}
              </router-link>
            </li>
            <template v-else>
              <li class="mr-6">
                <router-link :to="{ name: 'login' }">
                  {{ $t('login') }}
                </router-link>
              </li>
              <li>
                <router-link :to="{ name: 'register' }">
                  {{ $t('register') }}
                </router-link>
              </li>
            </template>
          </ul>
        </container>
      </layout-navigation>
      <layout-main class="h-full flex items-center justify-center">
        <nuxt/>
      </layout-main>
    </layout-container>
  </layout-container>
</template>

<script>
import { mapGetters } from 'vuex'
import Logo from '@/components/Logo'
import LocaleDropdown from '@/components/LocaleDropdown'

export default {
  components: {
    Logo,
    LocaleDropdown
  },
  data: () => ({
    appName: process.env.appName
  }),
  computed: mapGetters({
    user: 'auth/user',
    authenticated: 'auth/check'
  }),
}
</script>

