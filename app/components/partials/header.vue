<template>
  <header class="flex items-center py-4 md:py-8">
    <div class="header__logo">
      <nuxt-link to="/">
        <img :src="logo" alt="Logo" />
      </nuxt-link>
    </div>

    <nav class="nav ml-auto">
      <ul class="flex flex-row items-center sm:mt-4 sm:pt-4 md:mt-0 md:pt-0 md:mr-4 lg:mr-8">
        <li>
          <nuxt-link to="/blog" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
            Blog
          </nuxt-link>
        </li>
                    <li class="last">
            <a href="#">
              <nuxt-link to="/about"
                ><span class="title">About Us</span></nuxt-link
              ></a
            >
            <ul>
              <li><nuxt-link to="/blogs">Blog</nuxt-link></li>
              <li>
                <span>
                  <nuxt-link to="/faq">FAQ</nuxt-link>
                </span>
              </li>
              <li>
                <span>
                  <nuxt-link to="/testimonials">Testimonials</nuxt-link>
                </span>
              </li>
              <li>
                <span>
                  <nuxt-link to="/careers">Careers</nuxt-link>
                </span>
              </li>
              <li>
                <span>
                  <nuxt-link to="/referfriend">Refer a Friend</nuxt-link>
                </span>
              </li>
              <li>
                <span>
                  <nuxt-link to="/franchise-enquiry"
                    >Franchise Enquiry</nuxt-link
                  >
                </span>
              </li>
              <li>
                <span>
                  <nuxt-link to="/contacts">Contact Us</nuxt-link>
                </span>
              </li> 
            </ul>
          </li>
               
          <!-- <li>
          <nuxt-link to="/services" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
            Services
          </nuxt-link>
        </li> -->

        <li
          v-for="(page, index) in pages"
          :key="index"
          class="block font-medium px-4 py-1 md:p-2 lg:px-4"
        >
          <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Header extends Vue {
  get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss">
.nav {
  ul li > a {
    &.nuxt-link-active {
      color: $bluise;
      @apply font-bold;
    }
  }
}
</style>
