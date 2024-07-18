<template>
  <v-app :style="{background: $vuetify.theme.themes.light.colors.primary}">
    <v-main>
      <Navbar/>
      <v-container fluid>
        <v-row>
          <v-col cols="12" sm="2">
            <v-row>
              <v-col cols="12" sm="12">
                <v-expansion-panels v-model="panel">
                  <v-expansion-panel class="co">
                    <v-expansion-panel-title class="text-white bg-orange">
                      <v-icon icon="mdi mdi-menu" class="ml-n4 mr-1"></v-icon>
                      Category
                    </v-expansion-panel-title>
                  </v-expansion-panel>
                </v-expansion-panels>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
    <Footer/>
  </v-app>
</template>

<script setup>
  import Navbar from "@/components/Navbar.vue"
  import Footer from "@/components/Footer.vue";
</script>
