<template>
  <v-container class="text-center">
    <v-row class="text-center">
      <v-col sm="12" md="12">
        <h1 style="width:100%">
          Products
        </h1>
      </v-col>
    </v-row>
    <v-row>
      <!-- Breadcrumb with > divider between links -->
      <v-col sm="6" md="6">
        <v-breadcrumbs :items="breadCr" divider=">" />
      </v-col>
      <!-- Search bar -->
      <v-col sm="6" md="6">
        <v-text-field v-model="search" append-icon="search" label="Search" single-line hide-details>
        </v-text-field>
      </v-col>
    </v-row>
    <v-row>
      <!-- Placeholder for filters etc section of page -->
      <v-col xs="12" sm="3" md="3">
        <v-card>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="product-title">
                Two Toner 2
              </v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-img src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg" height="200" />
        </v-card>
      </v-col>
      <!-- Product Cards Section of Page -->
      <v-col sm="9" md="9">
        <v-data-iterator :items="items" :items-per-page.sync="itemsPerPage" :footer-props="{ itemsPerPageOptions }">
          <template v-slot:default="props">
            <v-row>
              <v-col v-for="item in props.items" :key="item.name" sm="4" md="3" class="pa-0">
                <v-card class="mx-2 mb-4">
                  <v-img src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg" height="200">
                    <v-card-title><h4 style="color:#ffffff;">{{ item.name }}</h4></v-card-title>
                  </v-img>
                  <v-divider />
                  <v-list dense>
                    <v-list-item>
                      <v-list-item-content>
                        Colour
                      </v-list-item-content>
                      <v-list-item-content class="align-end">
                        {{ item.colour }}
                      </v-list-item-content>
                    </v-list-item>
                    <v-list-item>
                      <v-list-item-content>Price:</v-list-item-content>
                      <v-list-item-content class="align-end">
                        {{ item.price }}
                      </v-list-item-content>
                    </v-list-item>
                  </v-list>
                </v-card>
              </v-col>
              <!-- <v-col v-for="n in 12" :key="n" class="pa-0" sm="4" md="3">
                  <v-card class="mx-2 mb-4">
                      <v-img
                      src="https://cdn.vuetifyjs.com/images/cards/mountain.jpg"
                      height="200"
                      class="white--text"
                      >
                          <v-card-title class="align-end fill-height">Dicey Dice</v-card-title>
                      </v-img>
                      <v-card-text class="text-left">Gemstone Violet and white marble effect generic product description</v-card-text>
                  </v-card>
              </v-col> -->
            </v-row>
          </template>
        </v-data-iterator>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    breadCr: [
      {
        text: 'Home',
        disabled: false,
        href: '/'
      },
      {
        text: 'Products',
        disabled: false,
        href: '/products'
      },
      {
        text: 'Link 2',
        disabled: true,
        href: '/'
      }
    ],

    itemsPerPageOptions: [4, 8, 12],
    itemsPerPage: 4,
    search: '',
    items: [
      {
        name: 'Amie',
        image: 'images/mountain.jpg',
        colour: 'Pink',
        price: 6.0
      },
      {
        name: 'Smells',
        colour: 'Green',
        price: 9.0
      },
      {
        name: 'Quite',
        colour: 'Pink',
        price: 16.0
      },
      {
        name: 'Strongly',
        colour: 'Orange',
        price: 3.7
      },
      {
        name: 'of',
        colour: 662,
        price: 16.0
      },
      {
        name: 'Sweetness',
        colour: 32,
        price: 0.0
      },
      {
        name: 'Lollipop',
        colour: 92,
        price: 0.2
      },
      {
        name: 'Honeycomb',
        colour: 372,
        price: 3.2
      },
      {
        name: 'Donut',
        colour: 2,
        price: 25.0
      },
      {
        name: 'KitKat',
        colour: 76,
        price: 26.0
      }
    ]
  })
}

</script>
