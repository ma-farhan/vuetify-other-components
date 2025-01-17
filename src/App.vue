<template>
  <v-container>

   <v-table fixed-header>
   <thead>
   <tr>
   <th class="text-left">Name</th>
   <th class="text-right">Calories</th>
   </tr>
   </thead>
   <tbody>
   <tr v-for="items in desserts" :key="items.name">
   <td>{{ items.name }}</td>
   <td>{{ items.calories }}</td>
   </tr>
   </tbody>
   </v-table>

  </v-container>
  <v-divider></v-divider>
  <v-container>
  <v-card>
  <v-tabs v-model="tab" bg-color="primary">
  <v-tab value="one">Item 1</v-tab>
  <v-tab value="two">Item 2</v-tab>
  <v-tab value="three">Item 3</v-tab>
  </v-tabs>
  
  
  <v-card-text>
  <v-tabs-window v-model="tab">
  <v-tabs-window-item value="one">one</v-tabs-window-item>
  <v-tabs-window-item value="two">two</v-tabs-window-item>
  <v-tabs-window-item value="three">three</v-tabs-window-item>
  </v-tabs-window>
  </v-card-text>
  </v-card>
  </v-container>
  
  
  
  
  <v-card>
  <v-tabs v-model="tab" bg-color="secondary" center-active="">
  <v-tab :value="1">LANDSCAPE</v-tab>
  <v-tab :value="2">CITY</v-tab>
  <v-tab :value="3">ABSTRACT</v-tab>
  </v-tabs>
  <v-tabs-window v-model="tab">
  <v-tabs-window-item v-for="n in 3" :key="n" :value="n">
  <v-container fluid>
  <v-row>
  <v-col v-for="i in 6" :key="i" cols="12" md="4">
  <v-img :lazy-src="`https://picsum.photos/10/6?image=${i * n * 5 + 10}`"
                 :src="`https://picsum.photos/500/300?image=${i * n * 5 + 10}`"
                 height="205"
                 cover>
  </v-img>
  </v-col>
  </v-row>
  </v-container>
  </v-tabs-window-item>
  </v-tabs-window>
  </v-card>
  
  
  <v-container>
  <v-card>
  <v-tabs bg-color="secondary" show-arrows>
  <v-tab v-for="i in 30" :key="i" :text="'item' + i">
  </v-tab>
  </v-tabs>
  </v-card>
  </v-container>
  
  
  
  
  <template>
  <div class="text-center pa-4">
    <v-btn @click="dialog = true"> Open Dialog </v-btn>

    <v-dialog v-model="dialog" width="auto">
      <v-card
        max-width="400"
        prepend-icon="mdi-update"
        text="Your application will relaunch automatically after the update is complete."
        title="Update in progress"
      >
        <template v-slot:actions>
          <v-btn class="ms-auto" text="Ok" @click="dialog = false"></v-btn>
        </template>
      </v-card>
    </v-dialog>
  </div>
</template>


  <IconHome/>
  <IconMicrophone/>
  <IconBrandGithubFilled/>
  
  
  
  
  
  
  <v-container>
  <v-app>
   <v-card
     class="mx-auto"
     href="https://github.com/vuetifyjs/vuetify/"
     max-width="344"
     rel="noopener"
     subtitle="Check out the official repository"
     target="_blank"
     title="Vuetify on GitHub"
   >
   <template #prepend>
       <IconBrandGithubFilled size="24" />
     </template>
  
  
     <template #append>
       <IconExternalLink size="24" />
     </template>
  
  
  
  
   </v-card>
  
  
  </v-app>
  </v-container>
  </template>
  
  
  <script setup>
  import { ref } from 'vue';
  import { IconHome,IconMicrophone,IconBrandGithubFilled, IconExternalLink } from '@tabler/icons-vue';
  
  
  const tab=ref()
  const dialog=ref(false)
  const desserts = ref([
   { name: 'Frozen Yogurt', calories: 159 },
   { name: 'Ice cream sandwich', calories: 237 },
   { name: 'Eclair', calories: 262 },
   { name: 'Cupcake', calories: 305 },
   { name: 'Gingerbread', calories: 356 },
   { name: 'Jelly bean', calories: 375 },
   { name: 'Lollipop', calories: 392 },
   { name: 'Honeycomb', calories: 408 },
   { name: 'Donut', calories: 452 },
   { name: 'KitKat', calories: 518 },
  ]);
  </script>
  
  