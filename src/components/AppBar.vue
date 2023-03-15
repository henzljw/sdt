<template>
    <v-app-bar app elevation="0" color="transparent">
        <v-spacer></v-spacer>
        <!-- Dark mode // Light mode icon button -->
        <v-btn icon v-if="!$vuetify.theme.dark" @click="toggleTheme()">
            <v-icon>mdi-lightbulb</v-icon>
        </v-btn>
        <v-btn icon v-if="$vuetify.theme.dark" @click="toggleTheme()">
            <v-icon color="yellow darken-3">mdi-lightbulb-on</v-icon>
        </v-btn>
        <!-- About sdt icon button -->
        <v-dialog persistent max-width="300" v-model="dialog">
            <template v-slot:activator="{ on, attrs }">
                <v-btn icon v-bind="attrs" v-on="on">
                    <v-icon>mdi-information</v-icon>
                </v-btn>
            </template>
            <v-card>
                <v-card-title>
                    About sdt
                </v-card-title>
                <v-card-text>
                    sdt is a live date and time viewer web application to show live date and time. It is
                    engineered with Vue.js framework and Vuetify framework, a Material Design framework for
                    Vue.js. The application is in beta stage so stay tuned for upcoming features to bake in
                    this application.
                </v-card-text>
                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn text @click="dialog = false">
                        Close
                    </v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>
        <!-- Github link -->
        <a href="https://github.com/henzljw/sdt" target="blank">
            <v-btn icon>
                <font-awesome-icon icon="fa-brands fa-github" size="xl" />
            </v-btn>
        </a>
    </v-app-bar>
</template>

<script>
export default {
    name: 'AppBar',
    data() {
        return {
            dialog: false,
        }
    },
    methods: {
        toggleTheme() {
            this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
        },
    },
}
</script>