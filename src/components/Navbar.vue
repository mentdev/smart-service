<template>   
    <nav>
        <v-app-bar flat>
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
            <v-toolbar-title class="grey--text">
                <span class="font-weight-light">UP </span>
                <span>Smart Services</span>
            </v-toolbar-title>
            
            <v-spacer></v-spacer>

            <v-menu offset-y>
                <template v-slot:activator="{ on }">
                    <v-btn text color="grey" v-on="on">
                        <v-icon>mdi-menu-down</v-icon>
                        <span>Menu</span>
                    </v-btn>
                </template>
                <v-list>
                    <v-list-item v-for="menu in links" :key="menu.text" router :to ="menu.route" >
                        <v-list-item-title>{{ menu.text }}</v-list-item-title>
                    </v-list-item>
                </v-list>
                
            </v-menu>
            <v-btn text color="grey">
                <span>Sign Out</span>
                <v-icon right>mdi-exit-to-app</v-icon>
            </v-btn>
        </v-app-bar>


        <v-navigation-drawer v-model="drawer" app class="indigo">
            <v-layout column align-center>
                <v-flex class="mt-5">
                    <v-avatar size="100">
                        <img src="/avatar-1.png" alt="">
                    </v-avatar>
                    <p class="white--text subheading mt-1">
                        Mentdev
                    </p>
                </v-flex>
            </v-layout>
            <v-list flat>
                <v-subheader class="white--text">REPORTS</v-subheader>
                <v-list-item-group>
                    <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
                        <v-list-item-icon>
                            <v-icon>{{ link.icon }}</v-icon>
                        </v-list-item-icon>
                        <v-list-item-content>
                            <v-list-item-title>{{ link.text }}</v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data(){
        return{
            drawer: false,
            links: [
                { icon: 'mdi-clock', text: 'การแจ้งซ่อม', route: '/'},
                { icon: 'mdi-account', text: 'Project', route: '/projects'},
                { icon: 'mdi-flag', text: 'Team', route: '/team'}
            ],
           
        }
    }
    
}
</script>