<template>
    <app-layout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="py-12">
                          <v-card>
                            <v-navigation-drawer
                              v-model="drawer"
                              :mini-variant.sync="mini"
                              permanent
                            >
                              <v-list-item class="px-2">
                                <v-list-item-title>John Leider</v-list-item-title>

                                <v-btn
                                  icon
                                  @click.stop="mini = !mini"
                                >
                                  <v-icon>mdi-chevron-left</v-icon>
                                </v-btn>
                              </v-list-item>

                              <v-divider></v-divider>

                              <v-list dense>
                                <v-list-item
                                  v-for="item in items"
                                  :key="item.title"
                                  link
                                >
                                  <v-list-item-icon>
                                    <v-icon>{{ item.icon }}</v-icon>
                                  </v-list-item-icon>

                                  <v-list-item-content>
                                    <v-list-item-title> <button>{{ item.title }}</button></v-list-item-title>
                                  </v-list-item-content>
                                </v-list-item>
                              </v-list>
                            </v-navigation-drawer>
                          </v-card>




        </div>
    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout'
    import Welcome from '@/Jetstream/Welcome'

    export default {
        components: {
            AppLayout,
            Welcome,
        },
        data () {
            return {
              drawer: false,
              items: [
                { title: 'Home', icon: 'mdi-home-city' },
                { title: 'My Account', icon: 'mdi-account' },
                { title: 'Users', icon: 'mdi-account-group-outline' },
              ],
              mini: true,
      }
    }
    }
</script>
