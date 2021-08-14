<template>
  <div id="bandas">
    <div class="galery pa-14 mt-1">
      <h2 class="banda mb-14">Nuestras Bandas</h2>
      <v-container>
        <v-row>
          <v-col cols="12" sm="4">
            <v-card class="mx-auto" max-width="344">
              <v-img src="../assets/audioslave.jpg" height="200px"></v-img>

              <v-card-title>
                Audioslave
              </v-card-title>

              <v-card-subtitle>
                Género: Grunge
              </v-card-subtitle>

              <v-card-actions>
                <v-btn color="orange lighten-2" text>
                  Historia
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon @click="show = !show">
                  <v-icon>{{
                    show ? "mdi-chevron-up" : "mdi-chevron-down"
                  }}</v-icon>
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <div v-show="show">
                  <v-divider></v-divider>

                  <v-card-text>
                    Audioslave fue un supergrupo estadounidense de rock
                    alternativo formado en Los Ángeles, California, en 2001 por
                    el vocalista de Soundgarden Chris Cornell, y la sección
                    instrumental de Rage Against the Machine: Tom Morello, Tim
                    Commerford y Brad Wilk.
                  </v-card-text>
                </div>
              </v-expand-transition>
            </v-card>
          </v-col>

          <v-col cols="12" sm="4">
            <v-card class="mx-auto" max-width="344">
              <v-img src="../assets/Daft_Punk.jpg" height="200px"></v-img>

              <v-card-title>
                Daft Punk
              </v-card-title>

              <v-card-subtitle>
                Género: Dance-Electrónica
              </v-card-subtitle>

              <v-card-actions>
                <v-btn color="orange lighten-2" text>
                  Historia
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon @click="show2 = !show2">
                  <v-icon>{{
                    show2 ? "mdi-chevron-up" : "mdi-chevron-down"
                  }}</v-icon>
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <div v-show="show2">
                  <v-divider></v-divider>

                  <v-card-text>
                    Daft Punk fue un dúo formado por los músicos franceses Guy
                    Manuel de Homem Christo y Thomas Bangalter, Daft Punk
                    alcanzó una gran popularidad en el estilo house a mediados
                    de la década de los años 90 en Francia y continuó con su
                    éxito los años siguientes, usando el estilo house y
                    synthpop.
                  </v-card-text>
                </div>
              </v-expand-transition>
            </v-card>
          </v-col>

          <v-col cols="12" sm="4">
            <v-card class="mx-auto" max-width="344">
              <v-img src="../assets/shakira.jpg" height="200px"></v-img>

              <v-card-title>
                shakira
              </v-card-title>

              <v-card-subtitle>
                Género: Pop
              </v-card-subtitle>

              <v-card-actions>
                <v-btn color="orange lighten-2" text>
                  Historia
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn icon @click="show3 = !show3">
                  <v-icon>{{
                    show3 ? "mdi-chevron-up" : "mdi-chevron-down"
                  }}</v-icon>
                </v-btn>
              </v-card-actions>

              <v-expand-transition>
                <div v-show="show3">
                  <v-divider></v-divider>

                  <v-card-text>
                    Shakira Isabel Mebarak Ripoll, conocida artísticamente como
                    Shakira, es una cantautora, bailarina, actriz, empresaria,
                    embajadora de buena voluntad de UNICEF y filántropa
                    colombiana.
                  </v-card-text>
                </div>
              </v-expand-transition>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    show: false,
    show2: false,
    show3: false,
  }),
};
</script>
<style>
.banda {
  text-align: center;
  color: grey;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}
</style>
