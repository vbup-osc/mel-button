<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" :mobile-breakpoint="1024" class="elevation-3" fixed app>
      <!--
      <template v-slot:img>
        <v-img />
        <div
          class="nav-darwer-overlay"
          :class="$vuetify.theme.dark ? 'nav-darwer-overlay-dark' : 'nav-darwer-overlay-light'"
        />
      </template>
      -->
      <v-list style="padding-top: 0;">
        <v-list-item to="/" router exact dense>
          <v-list-item-action>
            <v-icon>{{ icons.apps }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ $t('site.index') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item
          v-for="(item, i) in nav_items"
          :key="i"
          :href="item.to"
          target="_blank"
          rel="noreferrer"
          router
          exact
          dense
        >
          <v-list-item-action>
            <v-img :src="item.icon" style="width: 24px;" />
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <div v-if="current_locale === 'zh'">
        <v-divider />
        <v-list>
          <v-list-item
            v-for="item in external_cn"
            :key="item.to"
            dense
            :href="item.to"
            target="_blank"
            rel="noreferrer"
          >
            <v-list-item-action>
              <v-icon>{{ icons[item.icon] }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </div>
      <v-divider />
      <v-list>
        <v-list-item dense to="/links" router exact>
          <v-list-item-action>
            <v-icon>{{ icons.play_list_star }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ $t('site.links') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item dense to="/about" router exact>
          <v-list-item-action>
            <v-icon>{{ icons.code_tags }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ $t('site.about') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      dense
      class="primary white--text"
      :class="[this.$vuetify.theme.dark ? 'gradient-header-dark' : 'gradient-header-light']"
      app
    >
      <v-app-bar-nav-icon class="white--text" @click.stop="drawer = !drawer" />
      <v-toolbar-title v-text="$t('site.title') + ' 🌟'" />
      <v-spacer />
      <v-tooltip bottom>
        <template v-slot:activator="{ on }">
          <v-btn icon class="white--text" @click="switch_dark()" v-on="on">
            <v-icon>{{ icons.brightness }}</v-icon>
          </v-btn>
        </template>
        <span>{{ $t('site.switch_dark_mode') }}</span>
      </v-tooltip>
      <v-menu offset-y>
        <template v-slot:activator="{ on: menu }">
          <v-tooltip bottom>
            <template v-slot:activator="{ on: tooltip }">
              <v-btn icon class="white--text" v-on="{ ...tooltip, ...menu }">
                <v-icon>{{ icons.translate }}</v-icon>
              </v-btn>
            </template>
            <span>{{ $t('site.switch_language') }}</span>
          </v-tooltip>
        </template>
        <v-list>
          <v-list-item id="lang-switch-zh" @click="switch_lang('zh')">
            <v-list-item-title>简体中文</v-list-item-title>
          </v-list-item>
          <v-list-item id="lang-switch-ja" @click="switch_lang('ja')">
            <v-list-item-title>日本語</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
      <v-footer :fixed="false">
        <div>
          <div style="vertical-align: middle;">
            <!-- TODO 页脚 作者地址 仓库地址 -->
            <span>&copy;</span>
            <span>
              <a href="https://space.bilibili.com/490670563" target="_blank" rel="noreferrer">
                {{ $t('site.footer.union') }}
              </a>
            </span>
            <span>
              &
              <a href="https://github.com/voosc" target="_blank" rel="noreferrer">
                {{ $t('site.footer.voosc') }}
              </a>
            </span>
            <!-- TODO -->
            <v-btn
              icon
              href="https://github.com/vbup-osc/mel-button"
              target="_blank"
              style="vertical-align: middle;"
              rel="noreferrer"
            >
              <v-icon>{{ icons.github }}</v-icon>
            </v-btn>
          </div>
          <div>
            <p>{{ $t('site.footer.content') }}</p>
          </div>
        </div>
      </v-footer>
    </v-main>
    <console-message />
  </v-app>
</template>

<style lang="scss">
$blur-function: blur(3px);
.v-application {
  html[lang='ja'] & {
    font-family: $ja-body-fonts;
  }
  html[lang='zh'] & {
    font-family: $zh-body-fonts;
  }
}
.gradient-header-light {
  background-image: linear-gradient(120deg, #ffab00 0%, #fbc02d 100%) !important;
}
.gradient-header-dark {
  background-image: linear-gradient(120deg, #ffa000 0%, #f9a825 100%) !important;
}
.nav-drawer-img {
  width: auto;
  height: 100%;
  /*
  -webkit-filter: $blur-function;
  -moz-filter: $blur-function;
  -ms-filter: $blur-function;
  filter: $blur-function;
   */
}
.nav-darwer-overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
}
.nav-darwer-overlay-light {
  background-color: rgba(255, 255, 255, 0.8);
}
.nav-darwer-overlay-dark {
  background-color: rgba(0, 0, 0, 0.8);
}
a {
  text-decoration: none;
}
</style>

<script>
import ConsoleMessage from '../components/ConsoleMessage';
import {
  mdiApps,
  mdiCodeTags,
  mdiBrightness2,
  mdiTranslate,
  mdiGithub,
  mdiNewspaper,
  mdiAlphaBBox,
  mdiPlaylistStar
} from '@mdi/js';

export default {
  components: {
    ConsoleMessage
  },
  data() {
    return {
      icons: {
        apps: mdiApps,
        code_tags: mdiCodeTags,
        brightness: mdiBrightness2,
        translate: mdiTranslate,
        github: mdiGithub,
        newspaper: mdiNewspaper,
        alpha_b_box: mdiAlphaBBox,
        play_list_star: mdiPlaylistStar
      },
      drawer: false,
      fixed: false,
      /**
       * TODO
       * 各种外链
       */
      nav_items: [
        // {
        //   icon: '/img/youtube-fill.svg',
        //   title: 'Youtube',
        //   to: 'https://www.youtube.com/channel/UCD8HOxPs4Xvsm8H0ZxXGiBw'
        // },
        // {
        //   /*TODO*/
        //   icon: '/img/twitter-fill.svg',
        //   title: 'Twitter',
        //   to: 'https://twitter.com/yozoramel'
        // },
        // {
        //   icon: '/img/bilibili-fill.svg',
        //   title: 'Bilibili',
        //   to: 'https://space.bilibili.com/389856447'
        // }
      ],
      external_cn: [
        {
          icon: 'alpha_b_box',
          title: '夜空梅露的樱桃汁工厂',
          to: 'https://space.bilibili.com/490670563/'
        },
        {
          icon: 'newspaper',
          title: '樱桃汁工厂周报',
          to: 'https://www.bilibili.com/read/readlist/rl250085'
        }
      ]
    };
  },
  computed: {
    current_locale() {
      return this.$i18n.locale;
    },
    vercel_logo() {
      const mode = this.$vuetify.theme.dark ? 'dark' : 'light';
      return '/img/vercel/' + mode + '.svg';
    }
  },
  mounted() {
    this.$vuetify.theme.dark = this.$store.state.dark === 'true';
    if (window.innerWidth >= 1024) {
      this.drawer = true;
    }
  },
  methods: {
    switch_dark() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
      this.$store.commit('SET_DARK', this.$vuetify.theme.dark);
    },
    switch_lang(lang) {
      console.log('switching to ' + lang);
      this.$store.commit('SET_LANG', lang);
      this.$i18n.locale = lang;
    }
  },
  head() {
    return {
      htmlAttrs: {
        lang: this.current_locale
      }
    };
  }
};
</script>
