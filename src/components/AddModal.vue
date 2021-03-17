<template>
  <v-row justify="center">
    <v-dialog
      v-model="getPhoto.modal"
      fullscreen
      hide-overlay
      transition="dialog-bottom-transition"
    >
      <v-card>
        <v-toolbar
          dark
          color="primary"
        >
          <v-btn
            icon
            dark
            @click="getPhoto.modal = false"
          >
            <v-icon>mdi-close</v-icon>
          </v-btn>
          <v-toolbar-title>Settings</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items>
            <v-btn
              dark
              text
              @click="getPhoto.modal = false"
            >
              Save
            </v-btn>
          </v-toolbar-items>
        </v-toolbar>
        <v-list
          three-line
          subheader
        >
          <v-subheader>User Controls</v-subheader>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>Content filtering</v-list-item-title>
              <v-list-item-subtitle>Set the content filtering level to restrict apps that can be downloaded</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title>Password</v-list-item-title>
              <v-list-item-subtitle>Require password for purchase or use password to restrict purchase</v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>

      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
  // export default {
  //   data () {
  //     return {
  //       dialog: false,
  //       notifications: false,
  //       sound: true,
  //       widgets: false,
  //     }
  //   },
  // }
</script>

<script lang='ts'>
import { Component, Prop, Watch, Vue } from 'vue-property-decorator';

@Component({
  name: 'AddModal',
})
export default class AddModalVue extends Vue {
  private get getPhoto(): any {
    return this.$store.state.photo;
  }
}
</script>