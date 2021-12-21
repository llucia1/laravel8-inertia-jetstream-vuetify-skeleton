<template>
    <app-layout title="Users">
        
        <template #header>
            <div class="menu-head">
                <div>                
                    <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                        Tordesillas
                    </h2>
                </div>
                <div>
                    <jet-nav-link :href="route('dashboard')" :active="route().current('dashboard')">
                                    TORD 400KV
                    </jet-nav-link>
                </div>
                <div> 
                    <jet-nav-link :href="route('tordesillas')" :active="route().current('tordesillas')">
                                    Evento RCI
                    </jet-nav-link>
                </div>
            </div>
        </template>
        <div class="bodymain">
            <div class="bodymenu">
<!--                     <sidebar-menu :menu="menu" />
 -->
                        <sidebarmenu :menu="menu" />

            </div>
            <div class="bodycontent">
                <div class="py-12">
                    <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                        <div class="bg-white overflow-hidden shadow-xl sm:rounded-lg">
                            <welcome />
                        </div>
                    </div>
                </div>                
            </div>
            
        </div>
    </app-layout>
</template>

<script>
    import AppLayout from '@/Layouts/AppLayout.vue'
    import Welcome from '@/Jetstream/Welcome.vue'
/*     import sidebarmenu from 'vue-sidebar-menu'
 */
/*     import { SidebarMenu } from 'vue-sidebar-menu'
 */

    export default ({
        components: {

            AppLayout,
            Welcome,
            sidebarmenu
            

        },
        data() {
            return {
                menu: [
                        {
                            href: '/',
                            title: 'Dashboard',
                            icon: 'fa fa-user'
                        },
                        {
                            href: '#',
                            title: 'Charts',
                            icon: 'fa fa-chart-area'
                        }
                ],

                drawer: true,
                items: [
                  { title: 'Home', icon: 'mdi-home-city' },
                  { title: 'My Account', icon: 'mdi-account' },
                  { title: 'Users', icon: 'mdi-account-group-outline' },
                ],
                mini: true,
                    }
                }
    })
</script>


<style scoped>
  .menu-head {
    display: flex;
    justify-content: space-between;
    width: 100%;
  }
  .bodymain {
      display: flex;
  }
  .bodymenu {
      width: 25%;
  }
  .bodycontent {
      width: 75%;
  }


</style>
