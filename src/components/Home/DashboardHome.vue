<template>
    <v-main class="body">
        <div>
            <v-app-bar dark app fixed>
                <v-btn to="/home">
                    <v-icon class="ma-2">mdi-domain</v-icon>
                    <h2>Yasogami Hotel</h2>
                </v-btn>

                <v-spacer></v-spacer>
                <v-btn class="mark ma-1" to="/home">HOME</v-btn>
                <v-btn class="mark ma-1" to="/listkamar">PEMESANAN</v-btn>
                <v-btn class="mark ma-1" to="/profile">PROFILE</v-btn>
                <v-btn class="mark ma-1" to="/aboutus">ABOUT US</v-btn>
            </v-app-bar>

            <div class="bg"></div>
            <div class="fullheight pa-5">
                <router-view></router-view>
            </div>
        </div>

        <v-footer dark padless fixed>
            <v-card flat tile class="secondary white--text text-center">
                <v-card-text>
                <v-btn
                    v-for="(icon, i) in icons"
                    :key="i"
                    class="mx-4 white--text"
                    :href="icon.link"
                    target="_blank"
                    icon
                >
                    <v-icon size="24px">{{ icon.text }}</v-icon>
                </v-btn>
                </v-card-text>
                <v-divider></v-divider>
                <v-card-text class="white--text">
                    {{ new Date().getFullYear() }} — <strong>Yasogami Hotel</strong>
                </v-card-text>
                <v-btn small block color="error" plain to="/laporkanMasalah">Laporkan Masalah</v-btn>
            </v-card>
        </v-footer>
    </v-main>
</template>

<style>
    .bg {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0;
        left: 0;
        background: url(https://images.unsplash.com/photo-1517840901100-8179e982acb7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80);
        background-size: cover;
        transform: scale(1.1);
        filter: brightness(50%); 
    }
</style>

<style scoped>
    .v-card {
        width: 100%;
    }

    .flex-center {
        display: flex;
        align-items: center;
        justify-content: center;
    }

    footer {
        bottom: 0;
    }
</style>

<script>
    export default {
    data: () => ({

        icons: [
        {
            text: "mdi-facebook",
            link: "",
        },
        {
            text: "mdi-twitter",
            link: "",
        },
        {
            text: "mdi-linkedin",
            link: "",
        },
        {
            text: "mdi-instagram",
            link: "",
        },
        ],
    }),
    };
</script>