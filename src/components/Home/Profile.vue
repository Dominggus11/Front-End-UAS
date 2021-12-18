<template>
  <v-main>
    <v-card class="mx-auto" color="blue lighten" dark max-width="500">
      <v-card-title>
        <v-icon large left>mdi-account</v-icon>
        <span class="text-h6 font-weight-light">Profile</span>
      </v-card-title>
      <v-card-text align="center" class="text-h5 font-weight-bold">{{
        email
      }}</v-card-text>
      <v-card-actions>
        <v-list-item class="grow">
          <v-list-item-avatar color="grey darken-3">
            <v-img
              class="elevation-6"
              alt=""
              src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
            ></v-img>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title align="left">{{ user.name }}</v-list-item-title>
          </v-list-item-content>
          <v-row align="center" justify="end">
            <v-btn
              @click="editHandler(user)"
              outlined
              color="white"
              class="ma-2"
              >EDIT</v-btn
            >
            <v-btn @click="logout" outlined color="white" class="ma-2"
              >LOGOUT</v-btn
            >
          </v-row>
        </v-list-item>
      </v-card-actions>
    </v-card>
    <v-btn class="mark"
      ><a href="https://goo.gl/maps/hXPEduDrpKhLR3PK9">Hotel LOcation</a>
    </v-btn>
    <v-dialog v-model="dialog" persistent max-width="600px">
      <v-card>
        <v-card-title>
          <span class="headline">{{ formTitle }} User </span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-text-field
              v-model="form.email"
              label="Email"
              required
              disabled
            ></v-text-field>
            <v-text-field
              v-model="form.name"
              label="Name"
              required
            ></v-text-field>
            <v-text-field
              v-model="form.password"
              label="Password"
              type="password"
              required
            ></v-text-field>
          </v-container>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="cancel"> Cancel </v-btn>
          <v-btn color="blue darken-1" text @click="update"> Save </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-main>
</template>


<style scoped>
.mark {
  margin: 100px;
  color: #fff;
  border-color: rgb(255, 251, 0) !important;
  background-color: rgb(255, 251, 0) !important;
}
a {
  text-decoration: none;
  font-size: larger;
  font-family: Arial, Helvetica, sans-serif;
}
</style>


<script>
export default {
  name: "List",
  data() {
    return {
      name: localStorage.getItem("name"),
      email: localStorage.getItem("email"),
      password: localStorage.getItem("password"),
      inputType: "Ubah",
      load: false,
      error_message: "",
      color: "",
      dialog: false,
      dialogConfirm: false,

      user: new FormData(),
      users: [],
      form: {
        name: null,
        email: null,
        password: null,
      },
      deleteId: "",
      editId: "",
    };
  },
  methods: {
    logout() {
      localStorage.clear();
      // this.$router.push({
      //   name: "/userlogin",
      // });
      this.$router.push({ path: "/userlogin" });
    },

    readData() {
      var url = this.$api + "/user/" + localStorage.getItem("id");
      this.$http
        .get(url, {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        })
        .then((response) => {
          this.user = response.data.data;
        });
    },

    update() {
      let newData = {
        email: this.form.email,
        name: this.form.name,
        password: this.form.password,
      };

      var url = this.$api + "/user/" + this.editId;
      this.load = true;
      this.$http
        .put(url, newData, {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        })
        .then((response) => {
          this.error_message = response.data.message;
          this.color = "green";
          this.snackbar = true;
          this.load = false;
          this.close();
          this.readData();
          this.resetForm();
          this.inputType = "Ubah";
        })
        .catch((error) => {
          this.error_message = error.response.data.message;
          this.color = "red";
          this.snackbar = true;
          this.load = false;
        });
    },

    editHandler(user) {
      this.inputType = "Ubah";
      this.editId = user.id;
      this.form.email = user.email;
      this.form.name = user.name;
      this.form.password = user.password;
      this.dialog = true;
    },

    close() {
      this.dialog = false;
      this.inputType = "Ubah";
      this.dialogConfirm = false;
      this.readData();
    },

    cancel() {
      this.resetForm();
      this.readData();
      this.dialog = false;
      this.dialogConfirm = false;
      this.inputType = "Ubah";
    },

    resetForm() {
      this.form = { tipe_kamar: null, kapasitas: null, harga: null };
    },
  },
  computed: {
    formTitle() {
      return this.inputType;
    },
  },
  mounted() {
    this.readData();
  },
};
</script>