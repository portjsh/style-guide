<template>
  <v-container>
    <v-layout text-xs-center wrap>
      <v-flex xs12 class="container" v-for="sections in colors" :key="sections.name">
        <div class="section" v-for="section in sections" :key="section.name">
          <h4>{{section.name}}</h4>
          <div v-for="color in section.data" :key="color.id" class="color-wrapper">
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
              >{{color.hex}}</p>
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
              id: 1,
              class: "shells",
              headline: "Shells",
              hex: "#7123D9",
              var: "--color-shells"
            },
            {
              id: 2,
              class: "mermaid",
              headline: "Mermaid",
              hex: "#bb29bb",
              var: "--color-mermaid"
            },
            {
              id: 3,
              class: "ariel",
              headline: "Ariel",
              hex: "#f8e9f8",
              var: "--color-ariel"
            },
            {
              id: 4,
              class: "elsa",
              headline: "Elsa",
              hex: "#e0f6f7",
              var: "--color-elsa"
            },
            {
              id: 5,
              class: "dryink",
              headline: "Dry Ink",
              hex: "#63666a",
              var: "--color-dryink"
            },

            {
              id: 6,
              class: "blackhole",
              headline: "Black Hole",
              hex: "#272525",
              var: "--color-blackhole"
            },
            {
              id: 7,
              class: "coal",
              headline: "Coal",
              hex: "#444444",
              var: "--color-coal"
            }
          ]
        }
      },
      {
        section: {
          name: "Grays",
          data: [
            {
              id: 8,
              class: "ash",
              headline: "Ash",
              hex: "#979797",
              var: "--color-ash"
            },
            {
              id: 9,
              class: "pencil",
              headline: "Pencil",
              hex: "#646464",
              var: "--color-pencil"
            },
            {
              id: 10,
              class: "dust",
              headline: "Dust",
              hex: "#f4f4f4",
              var: "--color-dust"
            },
            {
              id: 11,
              class: "eyore",
              headline: "Eyore",
              hex: "#bbbcbc",
              var: "--color-eyore"
            },
            {
              id: 12,
              class: "steel",
              headline: "Steel",
              hex: "#ced0d0",
              var: "--color-steel"
            },
            {
              id: 13,
              class: "gandalf",
              headline: "Gandalf",
              hex: "#dadbdb",
              var: "--color-gandalf"
            },
            {
              id: 14,
              class: "londonfog",
              headline: "London Fog",
              hex: "#eceded",
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
              id: 15,
              class: "gandalfthewhite",
              headline: "Gandalf the White",
              hex: "#f6f7f7",
              var: "--color-gandalfthewhite"
            },
            {
              id: 16,
              class: "nuskinblue",
              headline: "Nuskin Blue",
              hex: "#008ab0",
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
              id: 17,
              class: "color-error",
              headline: "Error",
              hex: "#b2140a",
              var: "--color-error"
            },
            {
              id: 18,
              class: "progress-color",
              headline: "Progress",
              hex: "#22d55c",
              var: "--progress-color"
            },
            {
              id: 19,
              class: "warning-color",
              headline: "Warning",
              hex: "#fcbc00",
              var: "--warning-color"
            },
            {
              id: 20,
              class: "information-color",
              headline: "Infomation",
              hex: "#123DBA",
              var: "--information-color"
            },
            {
              id: 21,
              class: "notice-color",
              headline: "Notice",
              hex: "#35b2f0",
              var: "--notice-color"
            }
          ]
        }
      },
      {
        section: {
          name: "Expressive Colors",
          data: [
            {
              id: 22,
              class: "lemon",
              headline: "Lemon",
              hex: "#ffd700",
              var: "--lemon"
            },
            {
              id: 23,
              class: "lime",
              headline: "Lime",
              hex: "#c4d600",
              var: "--lime"
            },
            {
              id: 24,
              class: "lipstick",
              headline: "Lipstick",
              hex: "#ff00ad",
              var: "--lipstick"
            },
            {
              id: 25,
              class: "tangerine",
              headline: "Tagerine",
              hex: "#ff5e00",
              var: "--tagerine"
            },
            {
              id: 26,
              class: "poppy",
              headline: "Poppy",
              hex: "#e10098",
              var: "--poppy"
            },
            {
              id: 27,
              class: "sea-senor",
              headline: "Sea Senor",
              hex: "#00B5E2",
              var: "--sea-senor"
            },
            {
              id: 28,
              class: "magic",
              headline: "Magic",
              hex: "#BB29BB",
              var: "--magic"
            },
            {
              id: 30,
              class: "raspberry",
              headline: "Raspberry",
              hex: "#930093",
              var: "--raspberry"
            },
            {
              id: 31,
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
          name: "Main Theme",
          data: [
            {
              id: 52,
              class: "nuskinblue",
              headline: "Primary",
              hex: "#008AB0",
              var: "--color-primary"
            },
            {
              id: 53,
              class: "blackhole",
              headline: "Primary Text",
              hex: "#272525",
              var: "--color-primary-text"
            },
            {
              id: 54,
              class: "progress-color",
              headline: "Color Progress",
              hex: "#22D55C",
              var: "--color-progess"
            },
            {
              id: 55,
              class: "warning-color",
              headline: "Color Warning",
              hex: "#FCBC00",
              var: "--color-warning"
            },
            {
              id: 56,
              class: "information-color",
              headline: "Color Information",
              hex: "#123DBA",
              var: "--color-information"
            },
            {
              id: 57,
              class: "eyore",
              headline: "Gray 1",
              hex: "#BBBCBC",
              var: "--color-gray-1"
            },
            {
              id: 58,
              class: "steel",
              headline: "Gray 2",
              hex: "#CED0D0",
              var: "--color-gray-2"
            },
            {
              id: 59,
              class: "gandalf",
              headline: "Gray 3",
              hex: "#DADBDB",
              var: "--color-gray-3"
            },
            {
              id: 60,
              class: "lodonfog",
              headline: "Gray 4",
              hex: "#ECEDED",
              var: "--color-gray-4"
            },
            {
              id: 61,
              class: "pencil",
              headline: "Gray 5",
              hex: "#646464",
              var: "--color-gray-5"
            },
            {
              id: 62,
              class: "dust",
              headline: "Gray 6",
              hex: "#F4F4F4",
              var: "--color-gray-6"
            },
            {
              id: 63,
              class: "gandalfthewhite",
              headline: "Background 1",
              hex: "#F6F7F7",
              var: "--color-background-1"
            },
            {
              id: 64,
              class: "nuskinblue",
              headline: "Background 2",
              hex: "#008AB0",
              var: "--color-background-2"
            },
            {
              id: 65,
              class: "shells",
              headline: "Interative 1",
              hex: "#7123D9",
              var: "--color-interactive-1"
            },
            {
              id: 66,
              class: "mermaid",
              headline: "Interative 2",
              hex: "#BB29BB",
              var: "--color-interactive-2"
            },
            {
              id: 67,
              class: "raspberry",
              headline: "Interative 3",
              hex: "#930093",
              var: "--color-interactive-3"
            },
            {
              id: 68,
              class: "ariel",
              headline: "Interative 4",
              hex: "#F8E9F8",
              var: "--color-interactive-4"
            },
            {
              id: 69,
              class: "elsa",
              headline: "Interative 5",
              hex: "#E0F6F7",
              var: "--color-interactive-5"
            },
            {
              id: 70,
              class: "white",
              headline: "Interative 6",
              hex: "#FFFFFF",
              var: "--color-interactive-6"
            },
            {
              id: 71,
              class: "blackhole",
              headline: "Interative 7",
              hex: "#272525",
              var: "--color-interactive-7"
            },
            {
              id: 72,
              class: "dryink",
              headline: "Interative 8",
              hex: "#63666A",
              var: "--color-interactive-8"
            },
            {
              id: 73,
              class: "coal",
              headline: "Interative 9",
              hex: "#444444",
              var: "--color-interactive-9"
            },
            {
              id: 74,
              class: "lemon",
              headline: "Expressive 1",
              hex: "#FFD700",
              var: "--color-expressive-1"
            },
            {
              id: 75,
              class: "lime",
              headline: "Expressive 2",
              hex: "#C4D600",
              var: "--color-expressive-2"
            },
            {
              id: 76,
              class: "tangerine",
              headline: "Expressive 3",
              hex: "#FF5E00",
              var: "--color-expressive-3"
            },
            {
              id: 77,
              class: "poppy",
              headline: "Expressive 4",
              hex: "#E10098",
              var: "--color-expressive-4"
            },
            {
              id: 78,
              class: "sea-senor",
              headline: "Expressive 5",
              hex: "#00B5E2",
              var: "--color-expressive-5"
            },
            {
              id: 79,
              class: "magic",
              headline: "Expressive 6",
              hex: "#BB29BB",
              var: "--color-expressive-6"
            },
            {
              id: 80,
              class: "raspberry",
              headline: "Expressive 7",
              hex: "#930093",
              var: "--color-expressive-7"
            },
            {
              id: 81,
              class: "astronomy",
              headline: "Expressive 8",
              hex: "#440099",
              var: "--color-expressive-8"
            }
          ]
        }
      },
      {
        section: {
          name: "Deprecated Colors",
          data: [
            {
              id: 32,
              class: "babe",
              headline: "Babe",
              hex: "#37b0c9",
              var: "--babe"
            },
            {
              id: 33,
              class: "boringblue",
              headline: "Boring Blue",
              hex: "#b9e1ea",
              var: "--boringblue"
            },
            {
              id: 34,
              class: "elf",
              headline: "Elf",
              hex: "#e7faff",
              var: "--elf"
            },
            {
              id: 35,
              class: "blossom",
              headline: "Blossom",
              hex: "#ff76b9",
              var: "--blossom"
            },
            {
              id: 36,
              class: "aqua",
              headline: "Aqua",
              hex: "#1CD8D2",
              var: "--aqua"
            },
            {
              id: 37,
              class: "dusk",
              headline: "Dusk",
              hex: "#007298",
              var: "--dusk"
            },
            {
              id: 38,
              class: "white",
              headline: "White",
              hex: "#FFFFFF",
              var: "--white"
            },
            {
              id: 39,
              class: "black",
              headline: "Black",
              hex: "#000000",
              var: "--black"
            },
            {
              id: 41,
              class: "cheddar",
              headline: "Cheddar",
              hex: "#FFD700",
              var: "--cheddar"
            },
            {
              id: 42,
              class: "success",
              headline: "Success",
              hex: "#6BC56A",
              var: "--success"
            },
            {
              id: 43,
              class: "redshirt",
              headline: "Red Shirt",
              hex: "#C23934",
              var: "--redshirt"
            },
            {
              id: 44,
              class: "olive",
              headline: "Olive",
              hex: "#7D740C",
              var: "--olive"
            },
            {
              id: 45,
              class: "redshirt-dark",
              headline: "Red Shirt Dark",
              hex: "#7D740C",
              var: "--redshirt-dark"
            },
            {
              id: 46,
              class: "cheddar-dark",
              headline: "Cheddar Dark",
              hex: "#F9B249",
              var: "--cheddar-dark"
            },
            {
              id: 47,
              class: "success-dark",
              headline: "Success Dark",
              hex: "#64A262",
              var: "--success-dark"
            },
            {
              id: 48,
              class: "aqua-dark",
              headline: "Aqua Dark",
              hex: "#1F9FBE",
              var: "--aqua-dark"
            },
            {
              id: 49,
              class: "seafoam-light",
              headline: "Seafoam Light",
              hex: "#93EDC7",
              var: "--seafoam-light"
            },
            {
              id: 50,
              class: "sunset-dark",
              headline: "Sunset Dark",
              hex: "#9349B4",
              var: "--sunset-dark"
            },
            {
              id: 51,
              class: "sunset-light",
              headline: "Sunset Light",
              hex: "#FF8782",
              var: "--sunset-light"
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
