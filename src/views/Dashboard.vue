<template>
    <div class="dashboard">
        <v-alert
        dense
        text
        type="success"
    >
        <strong>Login successfully: </strong> Welcome...
    </v-alert>
        <v-subheader class="d-flex justify-space-between align-center">
            <h3>Dashboard</h3>

            <v-btn color="primary" class="rounded-lg">View Orders</v-btn>
        </v-subheader>
        <v-row>
            <v-col lg="7" cols="12">
                <v-row>
                    <v-col lg="6" cols="12" v-for="(item,index) in activities" :key="index">
                        <v-card elevation="2" class="rounded-lg">
                            <v-card-text class="d-flex justify-space-between align-center">
                                <div class="">
                                    <strong>{{item.title}}</strong><br>
                                    <small>{{item.temps}}</small>
                                </div>

                                <v-avatar :color="item.color" size="60">
                                    <span class="white--text _total">{{item.amounts}}</span>
                                </v-avatar>
                            </v-card-text>
                        </v-card>
                    </v-col>
                </v-row>
            </v-col>

            <v-col lg="5" cols="12">
                <v-card>
                    <v-card-title>Activities</v-card-title>
                    <v-timeline
                        align-top
                        dense
                    >
                        <v-timeline-item
                            color="blue"
                            small
                        >
                            <v-row class="pt-1">
                                <v-col>
                                    <strong>New Icon</strong>
                                    <div class="text-caption">
                                        60 minutes ago!
                                    </div>
                                </v-col>
                            </v-row>
                        </v-timeline-item>

                        <v-timeline-item
                            color="teal lighten-3"
                            small
                        >
                            <v-row class="pt-1">
                                <v-col>
                                    <strong>New Icon</strong>
                                    <div class="text-caption">
                                        45 minutes ago!
                                    </div>
                                </v-col>
                            </v-row>
                        </v-timeline-item>

                        <v-timeline-item
                            color="pink"
                            small
                        >
                            <v-row class="pt-1">
                                <v-col>
                                    <strong>New Icon</strong>
                                    <div class="text-caption">
                                        30 minutes ago!
                                    </div>
                                </v-col>
                            </v-row>
                        </v-timeline-item>

                    </v-timeline>
                </v-card>
            </v-col>
        </v-row>
        <v-subheader class="d-flex justify-space-between align-center">
            <h3>Recent Orders</h3>

            <v-btn color="success" class="rounded-lg">Add Product</v-btn>
        </v-subheader>
        
        <v-row>
            
            <v-col lg="12">
                <v-data-table
                    :headers="headers"
                    :items="desserts"
                    :items-per-page="5"
                    class="elevation-1"
                >
                    <template v-slot:item.action>
                        <v-btn color="success" small>View</v-btn>
                    </template>
                </v-data-table>
            </v-col>
        </v-row>
    </div>
</template>
<script>
export default {
    name: "Dashboard",
    data() {
        return{
            activities:[
                {title: 'Total Products', temps: 'Last 2 weeks', color: 'pink', amounts: 4560},
                {title: 'Total Category', temps: 'Last 1 week', color: 'deep-purple', amounts: 50},
                {title: 'Total Orders', temps: 'Last 4 days', color: 'green', amounts: 120},
                {title: 'Pending Orders', temps: 'Last 4 weeks', color: 'cyan', amounts: 4560},
                {title: 'Total Orders', temps: 'Last 4 days', color: 'primary', amounts: 4560},
                {title: 'Pending Orders', temps: 'Last 4 weeks', color: 'indigo', amounts: 4560},
            ],
            headers: [
                {
                    text: 'Dessert (100g serving)',
                    align: 'start',
                    sortable: false,
                    value: 'name',
                },
                { text: 'Calories', value: 'calories' },
                { text: 'Fat (g)', value: 'fat' },
                { text: 'Carbs (g)', value: 'carbs' },
                { text: 'Protein (g)', value: 'protein' },
                { text: 'Iron (%)', value: 'iron' },
                { text: 'Action', value: 'action' },
            ],
            desserts: [
                {
                    name: 'Frozen Yogurt',
                    calories: 159,
                    fat: 6.0,
                    carbs: 24,
                    protein: 4.0,
                    iron: '1%',
                },
                {
                    name: 'Ice cream sandwich',
                    calories: 237,
                    fat: 9.0,
                    carbs: 37,
                    protein: 4.3,
                    iron: '1%',
                },
                {
                    name: 'Eclair',
                    calories: 262,
                    fat: 16.0,
                    carbs: 23,
                    protein: 6.0,
                    iron: '7%',
                },
                {
                    name: 'Cupcake',
                    calories: 305,
                    fat: 3.7,
                    carbs: 67,
                    protein: 4.3,
                    iron: '8%',
                },
                {
                    name: 'Gingerbread',
                    calories: 356,
                    fat: 16.0,
                    carbs: 49,
                    protein: 3.9,
                    iron: '16%',
                },
                {
                    name: 'Jelly bean',
                    calories: 375,
                    fat: 0.0,
                    carbs: 94,
                    protein: 0.0,
                    iron: '0%',
                },
                {
                    name: 'Lollipop',
                    calories: 392,
                    fat: 0.2,
                    carbs: 98,
                    protein: 0,
                    iron: '2%',
                },
                {
                    name: 'Honeycomb',
                    calories: 408,
                    fat: 3.2,
                    carbs: 87,
                    protein: 6.5,
                    iron: '45%',
                },
                {
                    name: 'Donut',
                    calories: 452,
                    fat: 25.0,
                    carbs: 51,
                    protein: 4.9,
                    iron: '22%',
                },
                {
                    name: 'KitKat',
                    calories: 518,
                    fat: 26.0,
                    carbs: 65,
                    protein: 7,
                    iron: '6%',
                },
            ],
        }
    }
}
</script>

<style scoped>
    ._total{
        font-weight: 900;
    }
    ._avatarTotal{
        background: rgb(0, 92, 128);
    }
</style>