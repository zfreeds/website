<template>
  <section>
    <div class="top">
      <gradient-br />

      <sys-header-2>HARDWARE WITH POP!_OS</sys-header-2>
    </div>
    <div class="flexed">
      <div>
        <sys-subheader-2>Form of: An amazing computer.</sys-subheader-2>

        <sys-paragraph-1>
          System76 and the <a
            href="https://www.hpdevone.com/?utm_source=system76_pop&utm_medium=referral&utm_campaign=devone"
            target="_blank"
            rel="noopener"
            title="HP Dev One website"
          >HP Dev One</a> hardware are engineered together with Pop!_OS for optimal performance and user experience. These computers empower creators, makers, and builders to go forth and discover.
        </sys-paragraph-1>

        <sys-paragraph-1>
          Launch keyboard and Pop!_OS propel your ideas forward at max velocity. Customize your layout, pluck and place keycaps, turn down Caps Lock, and take your changes with you wherever you go.
        </sys-paragraph-1>
      </div>
      <div
        v-lazy-container="{ selector: 'img' }"
        class="grid"
      >
        <a
          :class="classes"
          href="https://system76.com/laptops"
          target="_blank"
          rel="noopener"
          title="Lemur"
        >
          <img
            alt="Lemur Pro"
            class="small thumbnail"
            :data-src="require('~/assets/images/index/thumbnail_lemp9.png?resize&sizes[]=300')"
          >
          <img
            class="brand"
            :data-srcset="require('~/assets/images/index/s76-logo.png?resize&sizes[]=40')"
          >
          <font-awesome-icon :icon="faExternalLinkAlt" />
        </a>

        <a
          :class="classes"
          href="https://system76.com/desktops"
          target="_blank"
          rel="noopener"
          title="Thelio"
        >
          <img
            alt="Thelio Desktops"
            class="thumbnail"
            :data-src="require('~/assets/images/index/thumbnail_thelios.png?resize&sizes[]=300')"
          >
          <img
            class="brand"
            :data-srcset="require('~/assets/images/index/s76-logo.png?resize&sizes[]=40')"
          >
          <font-awesome-icon :icon="faExternalLinkAlt" />
        </a>

        <a
          :class="classes"
          href="https://system76.com/accessories/launch"
          target="_blank"
          rel="noopener"
          title="Launch Keyboard"
        >
          <img
            alt="Launch Configurable Keyboard"
            class="thumbnail"
            :data-src="require('~/assets/images/index/thumbnail_launch.png?resize&sizes[]=300')"
          >
          <img
            class="brand"
            :data-srcset="require('~/assets/images/index/s76-logo.png?resize&sizes[]=40')"
          >
          <font-awesome-icon :icon="faExternalLinkAlt" />
        </a>

        <a
          :class="classes"
          href="https://www.hpdevone.com/?utm_source=system76_pop&utm_medium=referral&utm_campaign=devone"
          target="_blank"
          rel="noopener"
          title="HP Dev One"
        >
          <img
            alt="HP Dev One Laptop"
            class="thumbnail"
            :data-src="require('~/assets/images/index/thumbnail_hp-dev-one.png?resize&sizes[]=300')"
          >
          <img
            v-if="isLight"
            class="brand"
            :data-srcset="require('~/assets/images/index/hp-logo-black.png?resize&sizes[]=40')"
          >
          <img
            v-if="isDark"
            class="brand"
            :data-srcset="require('~/assets/images/index/hp-logo-white.png?resize&sizes[]=40')"
          >
          <font-awesome-icon :icon="faExternalLinkAlt" />
        </a>
      </div>
    </div>

    <gradient-br class="bottom" />
  </section>
</template>

<style scoped>
  section {
    margin: 4rem auto;
    max-width: 1280px;
    padding: 0 1rem;
  }

  .top {
    display: flex;
    flex-direction: column;
  }

  .top h2 {
    margin: 2rem 0 0;
  }

  section > h2,
  p {
    margin: 0;
  }

  .grid {
    align-content: stretch;
    align-items: stretch;
    display: grid;
    grid-gap: 1rem;
    grid-template-rows: repeat(4, 1fr);
    justify-content: stretch;
    margin: 1rem auto;
    padding: 0 1rem;
    text-align: center;
    user-select: none;
    width: 100%;
  }
  a {
    color: var(--color-orange);
  }
  .grid a {
    align-content: center;
    align-items: center;
    border-radius: 12px;
    border: 1px solid transparent;
    display: flex;
    justify-content: center;
    outline: none;
    position: relative;
    transition: box-shadow 250ms ease;
  }

  .grid a.light-mode {
    background-color: #fff;
    border-color: #C8C8C8;
    color: #272727;
  }

  .grid a.dark-mode {
    background-color: #272727;
    border-color: #171717;
    color: #ccc;
  }

  .grid a:focus,
  .grid a:active {
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.15);
  }

  .grid img.thumbnail {
    width: 100%;
    max-width: 300px;
    padding: 2rem;
  }

  .grid img.small {
    padding: 3.5rem;
  }

  .grid svg {
    bottom: 0.5rem;
    height: 1rem;
    position: absolute;
    right: 0.5rem;
  }

  .brand {
    position: absolute;
    top: 16px;
    left: 16px;
    height: 40px;
    width: 40px;
  }

  .flexed > div:nth-child(1) p:last-child {
    margin-top: 1em;
  }

  .flexed > div:nth-child(1) h2  {
    margin-bottom: 2em;
  }

  .bottom {
    margin-top: 2em;
  }

  @media (width >= 970px) {
    .flexed {
      display: flex;
      flex-direction: row;
    }

    .flexed > div {
      width: 50%;
    }

    .flexed > div:nth-child(1) {
      padding-right: 2em;
    }

    .grid {
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: 1fr;
    }
  }

  @media (width >= 1200px) {
    .top {
      align-items: center;
      align-content: center;
      justify-content: stretch;
      flex-direction: row-reverse;
    }

    .top h2 {
      flex: 0 0 auto;
      margin: 0 1rem 0 0;
    }
  }
</style>

<script>
  import { faExternalLinkAlt } from '@fortawesome/free-solid-svg-icons'
  import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

  import GradientBr from '~/components/gradient-br'
  import color from '~/mixins/color'

  export default {
    components: {
      FontAwesomeIcon,
      GradientBr
    },

    mixins: [
      color
    ],

    computed: {
      faExternalLinkAlt: () => faExternalLinkAlt
    }
  }
</script>
