<template>
  <main>
    <v-container fluid fill-height class="posisinya">
      <v-layout flex align-center justify-center>
        <v-flex xs12 sm6 elevation-6>
          <v-toolbar class="grey darken-3">
            <v-toolbar-title class="white--text">
              <h3>Masalah yang ditemukan</h3>
            </v-toolbar-title>
          </v-toolbar>
          <v-card>
            <v-card-text class="pt-4">
              <div>
                <v-form v-model="valid" ref="form">
                  <v-select
                    v-model="form.priority"
                    :items="items"
                    label="Priority"
                    required
                  ></v-select>
                  <v-text-field
                    label="Masalah"
                    v-model="form.catatan"
                    required
                  ></v-text-field>
                  <v-layout justify-end>
                    <v-spacer></v-spacer>
                    <v-btn
                      class="mr-2"
                      @click="setForm"
                      :class="{
                        'grey darken-1 white--text': valid,
                        disabled: !valid,
                      }"
                      >Laporkan</v-btn
                    >
                  </v-layout>
                </v-form>
              </div>
            </v-card-text>
          </v-card>
          <v-snackbar v-model="snackbar" :color="color" timeout="2000" bottom>
            {{ error_message }}</v-snackbar
          >
        </v-flex>
      </v-layout>
    </v-container>
  </main>
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
      items: ["Penting", "Biasa", "Tidak Penting"],
      note: new FormData(),
      notes: [],
      form: {
        priority: null,
        catatan: null,
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
    save() {
      this.note.append("bidang", this.form.priority);
      this.note.append("catatan", this.form.catatan);

      var url = this.$api + "/note";
      this.load = true;
      this.$http
        .post(url, this.note, {
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
        bidang: this.form.priority,
        catatan: this.form.catatan,
      };

      var url = this.$api + "/note/" + this.editId;
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
  },
};
</script>