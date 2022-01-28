<template>
    <v-navigation-drawer v-model="drawer" class="_navigation" app>
        <div class="text-center pa-4 _logoH">
            <v-avatar class="mb-4" color="grey darken-1" size="64">
                <img aspect-ratio="40" src="https://randomuser.me/api/portraits/women/2.jpg">
            </v-avatar>

            <div>Kang So Ra</div>
        </div>

        <v-divider></v-divider>

        <v-list>
            <v-list-item-group v-for="[icon, text, link] in links"
                :key="icon">
                <v-list-item
                :to="link"
                link
                >
                    <v-list-item-icon>
                        <v-icon class="_icon">{{ icon }}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                        <v-list-item-title class="_text">{{ text }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
             </v-list-item-group>
        </v-list>
    </v-navigation-drawer>
</template>
<script>
export default {
    props:['drawer'],
    name: "Sidebar",
    data(){
        return {
            links: [
                ['mdi-desktop-mac-dashboard', 'Dashboard', '/'],
                ['mdi-account', 'Profile',  '/profile'],
                ['mdi-clipboard-list-outline', 'Product', '/products'],
                ['mdi-alert-octagon', 'Order', '/order'],
                ['mdi-cog', 'System setting', '/setting'],
            ],
        }
    }
}
</script>

<style scoped>
    ._navigation{
        background: rgb(6, 60, 83) !important;
        color: #fff;
    }
    ._logoH{
        background-color: rgb(6, 60, 83);
    }
    ._icon{
        color: #fff !important;
    }
    ._text{
        color: #fff;
    }

    .v-item--active .v-list-item--active{
        color: #fff;
    }
</style>