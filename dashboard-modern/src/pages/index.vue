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
                    <v-expansion-panel-text>
                      <v-list class="cat" density="compact">
                        <v-list-item
                          v-for="(item, i) in items"
                          :key="i"
                          :value="item"
                          color="orange"
                          variant="plain"
                          class="ml-n2 text-caption"
                        >
                          {{ item.text }}
                        </v-list-item>
                      </v-list>
                    </v-expansion-panel-text>
                  </v-expansion-panel>
                </v-expansion-panels>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card class="co">
                  <v-list lines="two" class="cat pro">
                    <v-list-subheader inset class="ml-n10 text-white">
                      Hot Products
                    </v-list-subheader>

                    <v-list-item
                      v-for="product in products"
                      :key="product.title"
                      :title="product.title"
                      color="red"
                    >
                      <v-list-item-subtitle
                        class="text-caption text-orange"
                      >{{ product.subtitle }}</v-list-item-subtitle>
                      <template v-slot:prepend>
                        <v-avatar variant="outlined" rounded="0" color="grey">
                          <v-img color="white" :src="product.image"></v-img>
                        </v-avatar>
                      </template>
                    </v-list-item>
                  </v-list>
                </v-card>
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

  const items = [
      { text: "Desserts" },
      { text: "Drinks" },
      { text: "Pasta" },
      { text: "Pizza" },
      { text: "Sandwiches" },
    ];
  
  const  products = [
      {
        title: "Pizza",
        subtitle: "$800.00",
        image: "3.png",
      },
      {
        title: "Cheese",
        subtitle: "$300.00",
        image: "11.png",
      },
      {
        title: "Drink",
        subtitle: "$200.00",
        image: "20.png",
      },
      {
        title: "Drink2",
        subtitle: "$180.00",
        image: "21.png",
      },
      {
        title: "Dessert",
        subtitle: "$120.00",
        image: "7.png",
      },
    ];
</script>

<style scoped>
.co {
  background-color: #1f1f1f;
}
.tb {
  background-color: #2f2f2f;
}

.cat {
  background-color: #1f1f1f;
  color: white;
}
.tag:hover {
  color: orange;
}
.btn {
  background-color: #111111;
}
.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: 0.9;
  position: absolute;
  width: 100%;
}
</style>