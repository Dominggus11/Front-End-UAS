<template>
  <v-main class="list">
    <template>
      <v-layout row wrap>
        <v-flex class="pa-5" v-for="data in kamars" :key="data.id">
          <v-card class="mx-auto" max-width="400">
            <v-img
              src="https://cdna.artstation.com/p/assets/images/images/014/081/626/large/berktan-hatiboglu-modern-render1.jpg?1542377257"
              height="200px"
            ></v-img>
            <v-list-item two-line>
              <v-list-item-content>
                <v-list-item-title class="text-h6">
                  {{ data.tipe_kamar }}
                </v-list-item-title>
                <v-list-item-subtitle class="text-h7"
                  >Kapasitas: {{ data.kapasitas }}</v-list-item-subtitle
                >
              </v-list-item-content>
            </v-list-item>
            <v-divider></v-divider>
            <v-card-subtitle class="text-h5"
              >Rp. {{ data.harga }}</v-card-subtitle
            >
          </v-card>
        </v-flex>
      </v-layout>
    </template>
    <v-snackbar v-model="snackbar" :color="color" timeout="2000" bottom>{{
      error_message
    }}</v-snackbar>
  </v-main>
</template>

<script>
export default {
  name: "List",
  data() {
    return {
      inputType: "Tambah",
      load: false,
      snackbar: false,
      error_message: "",
      color: "",
      search: null,
      dialog: false,
      dialogConfirm: false,
      headers: [
        {
          text: "Tipe Kamar",
          align: "start",
          sortable: true,
          value: "tipe_kamar",
        },
        { text: "Kapasitas", value: "kapasitas" },
        { text: "Harga", value: "harga" },
        { text: "URL Photo", value: "urlPhoto" },
        { text: "Actions", value: "actions" },
      ],
      kamar: new FormData(),
      kamars: [],
      form: {
        tipe_kamar: null,
        kapasitas: null,
        harga: null,
        urlPhoto: null,
      },
      deleteId: "",
      editId: "",
    };
  },
  methods: {
    setForm() {
      if (this.inputType !== "Tambah") {
        this.update();
      } else {
        this.save();
      }
    },

    readData() {
      var url = this.$api + "/kamar";
      this.$http
        .get(url, {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        })
        .then((response) => {
          this.kamars = response.data.data;
        });
    },

    save() {
      this.kamar.append("tipe_kamar", this.form.tipe_kamar);
      this.kamar.append("kapasitas", this.form.kapasitas);
      this.kamar.append("harga", this.form.harga);
      this.kamar.append("urlPhoto", this.form.urlPhoto);

      var url = this.$api + "/kamar";
      this.load = true;
      this.$http
        .post(url, this.kamar, {
          headers: {
            Authorization: "Bearer " + localStorage.getItem("token"),
          },
        })
        .then((response) => {
          this.error_message = response.data.message;
          this.color = "green";
          this.snackbar = true;
          this.load = true;
          this.close();
          this.readData();
          this.resetForm();
        })
        .catch((error) => {
          this.error_message = error.response.data.message;
          this.color = "red";
          this.snackbar = true;
          this.load = false;
        });
    },

    update() {
      let newData = {
        tipe_kamar: this.form.tipe_kamar,
        kapasitas: this.form.kapasitas,
        harga: this.form.harga,
        urlPhoto: this.form.urlPhoto,
      };

      var url = this.$api + "/kamar/" + this.editId;
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
          this.inputType = "Tambah";
        })
        .catch((error) => {
          this.error_message = error.response.data.message;
          this.color = "red";
          this.snackbar = true;
          this.load = false;
        });
    },

    deleteData() {
      var url = this.$api + "/kamar/" + this.deleteId;
      this.load = true;
      this.$http
        .delete(url, {
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
          this.inputType = "Tambah";
        })
        .catch((error) => {
          this.error_message = error.response.data.message;
          this.color = "red";
          this.snackbar = true;
          this.load = false;
        });
    },

    editHandler(item) {
      this.inputType = "Ubah";
      this.editId = item.id;
      this.form.tipe_kamar = item.tipe_kamar;
      this.form.kapasitas = item.kapasitas;
      this.form.harga = item.harga;
      this.form.urlPhoto = item.urlPhoto;
      this.dialog = true;
    },
    deleteHandler(id) {
      this.deleteId = id;
      this.dialogConfirm = true;
    },
    close() {
      this.dialog = false;
      this.inputType = "Tambah";
      this.dialogConfirm = false;
      this.readData();
    },
    cancel() {
      this.resetForm();
      this.readData();
      this.dialog = false;
      this.dialogConfirm = false;
      this.inputType = "Tambah";
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