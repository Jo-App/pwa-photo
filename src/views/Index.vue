<template>
  <v-main>
    <v-card>
      <v-toolbar class="rounded-0" color="indigo" dark>
        <v-app-bar-nav-icon></v-app-bar-nav-icon>
        <v-toolbar-title>Discover</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </v-toolbar>

      <v-container fluid>
        <v-row dense>
          <v-col 
            cols="12" sm="6" md="4" lg="3" xl="2"
            v-for="item in this.aPictures" :key="item.key"
          >
            <v-card height="330px">
              <v-img :src="item.url" height="200px"></v-img>
              <v-card-title>
                <h1 class="ttitle gray--text text--darken-3 md-3">{{item.title}}</h1>
                <p class="body-2 grey--text">{{item.info}}</p>
              </v-card-title>
            </v-card>
            
          </v-col>
        </v-row>
      </v-container>
    </v-card>

    <v-btn @click="openModal()" color="blue" dark fixed bottom right fab>
      <v-icon>add</v-icon>
    </v-btn>
    
    <v-dialog v-model="getPhoto.modal">
      <AddModal v-if="getPhoto.modal"></AddModal>
    </v-dialog>
  </v-main>
</template>

<script lang='ts'>
import { Component, Prop, Watch, Vue } from 'vue-property-decorator';

import AddModal from '@/components/AddModal.vue';
import oPictureData from '@/datasources/picture-data';

@Component({
  name: 'Index',
  components: {
    AddModal,
  },
})
export default class IndexVue extends Vue {

  private get getPhoto(): any {
    return this.$store.state.photo;
  }

  private aPictures: any = oPictureData.aPictures;

  private openModal(): void {
    this.getPhoto.modal = !this.getPhoto.modal;
  }
}
</script>