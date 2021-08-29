<template>
  <div class="contact pa-16 my-15">
    <v-form
      v-model="btnEnabled"
      ref="form"
      @submit.prevent="sendEmail"
      id="contacto"
    >
      <div class="titulo" align="center" justify="center">
        <h1>Contacto</h1>
      </div>
      <v-container>
        <v-row>
          <v-col cols="12" sm="6">
            <div id="text-nombre">
              <v-text-field
                v-model="title"
                :rules=rulesRequired
                label="Tu Nombre"
                counter
                maxlength="20"
              ></v-text-field>
            </div>
          </v-col>

          <v-col cols="12" sm="6">
            <div id="text-email">
              <v-text-field
                v-model="email"
                :rules=rulesEmail
                label="E-mail"
              ></v-text-field>
            </div>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12" sm="12">
            <div id="text-asunto">
              <v-text-field
                v-model="asunto"
                :rules=rulesRequired
                label="Asunto"
                counter
                maxlength="20"
              ></v-text-field>
            </div>
          </v-col>
        </v-row>

        <div id="text-mensaje">
          <v-textarea
            counter
            v-model="message"
            label="Tu Mensaje"
            :rules=rulesMsj
            :value="value"
          ></v-textarea>
        </div>
        <v-btn
          class="boton mt-16"
          type="submit"
          elevation="1"
          v-bind:disabled="!btnEnabled"
          value="Send"
          >Enviar
        </v-btn>
        <a href="#nav">
              <button type="button" class="transition-swing v-btn v-btn--bottom v-btn--is-elevated v-btn--fab v-btn--fixed v-btn--has-bg v-btn--right v-btn--round theme--light v-size--large grey" aria-label="Vuelve al comienzo" title="Vuelve al comienzo" style="z-index: 6; margin-bottom: 89px; transform-origin: center center;"><span class="v-btn__content"><span aria-hidden="true" class="v-icon notranslate theme--light"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" role="img" aria-hidden="true" class="v-icon__svg"><path d="M7.41,15.41L12,10.83L16.59,15.41L18,14L12,8L6,14L7.41,15.41Z"></path></svg></span></span></button>
        </a>
        <v-card>
          <div class="exito">
            <v-snackbar
              v-model="exit"
              :timeout="5000"
              :value="true"
              absolute
              bottom
              color="success"
              centered
            >
              ¡Su mensaje ha sido enviado con exito!
            </v-snackbar>
          </div>
        </v-card>
      </v-container>
    </v-form>
  </div>
</template>

<script>
import emailjs from "emailjs-com";
//import{ init } from 'emailjs-com';
//init("user_edvq6QQiWcxDtb3NinDbC");

export default {
  // eslint-disable-next-line no-unused-vars
  data: (value) => ({
    btnEnabled: true,
    title: "",
    email: "",
    asunto: "",
    message: "",
    exit: false,
    value: "",

    rulesRequired: [(value) => !!value || "Por favor, complete el campo"],
    rulesMsj: [(value) => !!value || "Required"],
    rulesCounter: [(value) => value.length <= 20 || "Max 20 characters"],
    rulesEmail: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
  }),

  methods: {
    sendEmail(e) {
      if (this.$refs["form"].validate()) {
        this.btnEnabled = false;

        try {
          emailjs.sendForm(
            "service_oo2ukey",
            "template_vxzfy0r",
            e.target,
            "user_edvq6QQiWcxDtb3NinDbC",
            {
              name: this.name,
              email: this.email,
              asunto: this.asunto,
              message: this.message,
            }
            
          );
          this.btnEnviar()
        } catch (error) {
          console.log({ error });
        }
      }
    },

    btnEnviar() {
      this.title = "";
      this.email = "";
      this.asunto = "";
      this.message = "";
      this.rulesRequired = "";
      this.rulesEmail = "";
      this.rulesMsj= "";
      this.exit = true;

      setTimeout(() => {
        this.exit = false;
      }, 3000);
    },
  },
};
</script>

<style>
.boton {
  background: linear-gradient(0deg, #0f1111, #d6dedf, #505381);
  color: #ffffff;
}
.titulo {
  background: linear-gradient(0deg, #0f1111, #d6dedf, #7077d3);
  color: #000000;
}</style
>-->
