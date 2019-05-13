<template>
  <v-container>
    <v-layout text-xs-center wrap>
      <v-flex xs12 class="container" v-for="sections in colors" :key="sections.name">
        <div class="section" v-for="section in sections" :key="section.name">
          <h4>{{section.name}}</h4>
          <div v-for="(color, index) in section.data" :key="index" class="color-wrapper">
            <div class="left-side">
              <div class="square" :class="color.class"></div>
            </div>
            <div class="right-side">
              <p class="headline">{{color.headline}}</p>
              <p
                class="hex"
                v-clipboard:copy="color.hex"
                v-clipboard:success="onCopy"
                v-clipboard:error="onError"
              >{{color.hex}}</P>
              <p
                class="var"
                v-clipboard:copy="color.var"
                v-clipboard:success="onCopy"
                v-clipboard:error="onError"
              >{{color.var}}</p>
            </div>
          </div>
        </div>
      </v-flex>
      <v-flex sm12>
        <div class="progress-color feedback" v-if="copySucceeded === true">Copy Successful</div>
        <div class="color-error" v-if="copySucceeded === false && show === true">Copy Successful</div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    show: false,
    copySucceeded: null,
    colors: [
      {
        section: {
          name: "Interactive Colors",
          data: [
            {
              class: "shells",
              headline: "Shells",
              hex: "#7123D9",
              var: "--color-shells"
            },
            {
              class: "mermaid",
              headline: "Mermaid",
              hex: "#BB29BB",
              var: "--color-mermaid"
            },
            {
              class: "raspberry",
              headline: "Raspberry",
              hex: "#930093",
              var: "--color-raspberry"
            },
            {
              class: "ariel",
              headline: "Ariel",
              hex: "#F8E9F8",
              var: "--color-ariel"
            },
            {
              class: "blackhole",
              headline: "Black Hole",
              hex: "#272525",
              var: "--color-blackhole"
            },
            {
              class: "dryink",
              headline: "Dry Ink",
              hex: "#63666A",
              var: "--color-dryink"
            },
            {
              class: "white",
              headline: "White",
              hex: "#FFFFFF",
              var: "--color-white"
            },
            {
              class: "elsa",
              headline: "Elsa",
              hex: "#E0F6F7",
              var: "--color-elsa"
            }
          ]
        }
      },
      {
        section: {
          name: "Grays",
          data: [
            {
              class: "eyore",
              headline: "Eyore",
              hex: "#BBBCBC",
              var: "--color-eyore"
            },
            {
              class: "steel",
              headline: "Steel",
              hex: "#CED0D0",
              var: "--color-steel"
            },
            {
              class: "gandalf",
              headline: "Gandalf",
              hex: "#DADBDB",
              var: "--color-gandalf"
            },
            {
              class: "londonfog",
              headline: "London Fog",
              hex: "#ECEDED",
              var: "--color-londonfog"
            }
          ]
        }
      },
      {
        section: {
          name: "Background Colors",
          data: [
            {
              class: "gandalfthewhite",
              headline: "Gandalf the White",
              hex: "#F6F7F7",
              var: "--color-gandalfthewhite"
            },
            {
              class: "white",
              headline: "White",
              hex: "#FFFFFF",
              var: "--color-pencil"
            },
            {
              class: "nuskinblue",
              headline: "Nuskin Blue",
              hex: "#008AB0",
              var: "--color-pencil"
            }
          ]
        }
      },
      {
        section: {
          name: "Information Colors",
          data: [
            {
              class: "color-error",
              headline: "Error",
              hex: "#B2140A",
              var: "--color-error"
            },
            {
              class: "progress-color",
              headline: "Progress",
              hex: "#22D55C",
              var: "--progress-color"
            },
            {
              class: "warning-color",
              headline: "Warning",
              hex: "#FCBC00",
              var: "--warning-color"
            },
            {
              class: "information-color",
              headline: "Infomation",
              hex: "#123DBA",
              var: "--information-color"
            }
          ]
        }
      },
      {
        section: {
          name: "Expressive Colors",
          data: [
            {
              class: "lemon",
              headline: "Lemon",
              hex: "#FFD700",
              var: "--lemon"
            },
            {
              class: "lime",
              headline: "Lime",
              hex: "#C4D600",
              var: "--lime"
            },
            {
              class: "tangerine",
              headline: "Tagerine",
              hex: "#FF5E00",
              var: "--tagerine"
            },
            {
              class: "poppy",
              headline: "Poppy",
              hex: "#E10098",
              var: "--poppy"
            },
            {
              class: "sea-senor",
              headline: "Sea Senor",
              hex: "#00B5E2",
              var: "--sea-senor"
            },
            {
              class: "magic",
              headline: "Magic",
              hex: "#BB29BB",
              var: "--magic"
            },
            {
              class: "astronomy",
              headline: "Astronomy",
              hex: "#440099",
              var: "--astronomy"
            }
          ]
        }
      },
      {
        section: {
          name: "Non-Interface Colors",
          data: [
            {
              class: "annonation-1",
              hex: "#E3008A",
              var: "annonation-1"
            },
            {
              class: "annonation-2",
              hex: "#0040FF",
              var: "annonation-2"
            }
          ]
        }
      }
    ]
  }),
  methods: {
    onCopy: function() {
      this.copySucceeded = true;
      setTimeout(() => (this.copySucceeded = false), 1500);
    },
    onError: function() {
      this.copySucceeded = false;
    }
  },

  mounted: () => {}
};
</script>

<style  lang="scss" scoped>
@import "../scss/colors.scss";
</style>
