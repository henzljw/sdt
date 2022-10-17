<template>
    <v-app-bar app elevation="0">
        <v-spacer></v-spacer>
        <v-btn icon v-if="!$vuetify.theme.dark" @click="toggleTheme()">
            <v-icon class="mr-1" color="blue-grey darken-4">mdi-lightbulb</v-icon>
        </v-btn>
        <v-btn icon v-if="$vuetify.theme.dark" @click="toggleTheme()">
            <v-icon color="yellow darken-3">mdi-lightbulb-on</v-icon>
        </v-btn>
        <v-menu offset-y rounded-xl :close-on-click="closeOnClick">
            <template v-slot:activator="{ on, attrs }">
                <v-btn icon v-bind="attrs" v-on="on">
                    <v-icon>mdi-dots-vertical</v-icon>
                </v-btn>
            </template>
            <v-list>
                <v-list-item-group>
                    <v-dialog persistent max-width="300" v-model="dialog">
                        <template v-slot:activator="{ on, attrs }">
                            <v-list-item v-bind="attrs" v-on="on">
                                <v-list-item-content>
                                    <v-list-item-title>About</v-list-item-title>
                                </v-list-item-content>
                            </v-list-item>
                        </template>
                        <v-card>
                            <v-card-title>
                                About this website
                            </v-card-title>
                            <v-card-text>
                                This project is a mini project.
                            </v-card-text>
                            <v-card-actions>
                                <v-spacer></v-spacer>
                                <v-btn text @click="dialog = false">
                                    Ok
                                </v-btn>
                            </v-card-actions>
                        </v-card>
                    </v-dialog>
                </v-list-item-group>
            </v-list>
        </v-menu>
    </v-app-bar>
</template>

<script>
export default {
    name: 'AppBar',

    data() {
        return {
            dialog: false,
        }
        // closeOnClick: true,
    },

    methods: {
        toggleTheme() {
            this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
        }
    },
}
</script>