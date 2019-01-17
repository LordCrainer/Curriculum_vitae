<template>
  <v-container>
    <v-layout column>
      <v-flex>
        <v-card>
          <v-card-text class="text-md-center box">
            INFORMACIÓN PERSONAL
          </v-card-text>
          <v-card-text>
            <v-container>
              <v-layout wrap row>
                <v-flex xs12 sm8>
                  <v-flex xs12>
                    <v-layout
                      wrap
                      row
                      v-for="(datos, ind) in datosPersonales"
                      :key="ind"
                    >
                      <v-flex xs12 sm3>
                        <v-card-text class="text-sm-right pa-2 text-xs-center"
                          ><strong>{{ datos.titulo }}:</strong></v-card-text
                        >
                      </v-flex>
                      <v-flex xs12 sm9>
                        <v-card-text class="text-sm-left pa-2 text-xs-center">
                          {{ datos.nombre }}
                        </v-card-text>
                      </v-flex>
                    </v-layout>
                  </v-flex>
                </v-flex>
                <v-flex xs12 sm4>
                  <v-layout row justify-center align-center>
                    <v-flex xs12>
                      <v-hover>
                        <v-img
                          slot-scope="{
                            hover
                          }"
                          :class="`elevation-${hover ? 5 : 3}`"
                          height="200"
                          width="150"
                          src="https://uploads.codesandbox.io/uploads/user/17fffd86-3ee1-4ca9-abc0-4e76a2cb57f0/dfNi-img.jpg"
                          aspect-ratio="0.75"
                        ></v-img>
                      </v-hover>
                    </v-flex>
                  </v-layout>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-text>
        </v-card>
      </v-flex>
      <v-flex>
        <TimeCard :data="formacionAcademica">
          <v-card-text class="box" slot="tema">FORMACIÓN ACADÉMICA</v-card-text>
          <v-card-text
            class="text-xs-left pa-2"
            slot="time"
            slot-scope="tiempos"
          >
            {{ tiempos.item.inicio }} - {{ tiempos.item.fin }}
          </v-card-text>
          <v-card-text
            class="text-xs-left pa-2"
            slot="descripcion"
            slot-scope="info"
          >
            {{ info.item.descripcion }}
          </v-card-text>
        </TimeCard>
        <TimeCard :data="experienciaLaboral">
          <v-card-text class="box" slot="tema">EXPERIENCIA LABORAL</v-card-text>
          <v-card-text
            class="text-xs-left pa-2"
            slot="time"
            slot-scope="tiempos"
          >
            {{ tiempos.item.inicio }} - {{ tiempos.item.fin }}
          </v-card-text>
          <v-card-text
            class="text-xs-left pa-2"
            slot="descripcion"
            slot-scope="info"
          >
            {{ info.item.descripcion }}
          </v-card-text>
        </TimeCard>
        <TimeCard :data="conocimientos">
          <v-card-text class="box" slot="tema">CONOCIMIENTOS</v-card-text>
          <v-card-text
            slot="informacion"
            v-for="(conoc, index) in conocimientos"
            :key="index"
          >
            <v-card-title slot="titulo " class="title font-weight-bold pa-2">{{
              conoc.titulo
            }}</v-card-title>
            <v-divider></v-divider>
            <v-layout row>
              <v-flex xs4>
                <v-card-text class="text-xs-left pa-3 body-2 font-weight-bold"
                  >NOMBRE</v-card-text
                >
              </v-flex>
              <v-flex xs8>
                <v-card-text class="text-xs-left  pa-3 body-2 font-weight-bold"
                  >NIVEL</v-card-text
                >
              </v-flex>
            </v-layout>
            <v-layout row v-for="dato in conoc.dato" :key="dato.nombre">
              <v-flex xs4
                ><v-card-text class="text-xs-left pa-2 pl-3">{{
                  dato.nombre
                }}</v-card-text></v-flex
              >
              <v-flex xs8
                ><v-card-text class="text-xs-left pa-2 pl-3">{{
                  dato.nivel
                }}</v-card-text></v-flex
              >
            </v-layout>
          </v-card-text>
        </TimeCard>
      </v-flex>
    </v-layout>
  </v-container>
</template>
<script>
import TimeCard from "./../elementos/TimeCard.vue";
export default {
  components: { TimeCard },
  data() {
    return {
      datosPersonales: [
        { nombre: "Carlos Andrés", titulo: "NOMBRE" },
        { nombre: "García Morán", titulo: "APELLIDO" },
        { nombre: "0926795840", titulo: "CÉDULA" },
        { nombre: "30 de Junio de 1994", titulo: "FECHA" },
        { nombre: "camogan3000@hotmail.com", titulo: "EMAIL" },
        { nombre: "caangarc@espol.edu.ec", titulo: "EMAIL 2" },
        { nombre: "0967590148", titulo: "CELULAR" },
        { nombre: "5112460", titulo: "TELÉFONO" },
        {
          nombre: "Urb. San Antonio Mz9 Villa 7 Km 11.5 Vía Samborondón",
          titulo: "DIRECCIÓN"
        }
      ],
      formacionAcademica: [
        {
          inicio: 2019,
          fin: 2020,
          descripcion:
            "Cursando Decimo Semestre de la carrera Ingenería Electrónica y Telecomunicaciones en la Espol"
        },
        {
          inicio: 2006,
          fin: 2012,
          descripcion:
            "Certificado de Secundaria en el Colegio 'Centro Educativo Bilingüe Interamericano'"
        },
        {
          inicio: 2000,
          fin: 2006,
          descripcion: "Certificado de Primaria en El Libertador"
        }
      ],
      experienciaLaboral: [
        {
          inicio: 2012,
          fin: 2019,
          descripcion:
            "Profesor Particularde Matemáticas, Física, Química e Informática"
        },
        {
          inicio: 2012,
          fin: 2019,
          descripcion:
            "Diseñador Gráfico y modelado, tanto en el área de 2D y 3D."
        },
        {
          inicio: 2015,
          fin: 2018,
          descripcion:
            "Instalación y Configuración de equipos asociados al área de las telecomunicaciones y la seguridad, como antenas y cámaras de seguridad."
        },
        {
          inicio: 2015,
          fin: 2019,
          descripcion:
            "Desarrollador de Hardware usando PIC, Arduino y Raspberry Pi, para la realización de proyectos académicos de tercer nivel y cuarto nivel."
        },
        {
          inicio: 2015,
          fin: 2019,
          descripcion:
            "Desarrollador y Diseño de páginas web mediante el stack MEVN (Mongodb, Express.js, Vue.js y Node.js)."
        }
      ],
      conocimientos: [
        {
          titulo: "IDIOMA",
          dato: [
            { nivel: "Medio-Alto", nombre: "Inglés" },
            { nivel: "Alto", nombre: "Español" }
          ]
        },
        {
          titulo: "PROGRAMAS",
          dato: [
            { nombre: "Photoshop", nivel: "Medio" },
            { nombre: "Illustrator", nivel: "Medio" },
            { nombre: "Sketchup", nivel: "Medio-Alto" },
            { nombre: "Word", nivel: "Medio-Alto" },
            { nombre: "Power Point", nivel: "Alto" },
            { nombre: "Excel", nivel: "Medio-Alto" },
            { nombre: "Proteus", nivel: "Medio-Alto" },
            { nombre: "Ansys Electronic", nivel: "Medio" },
            { nombre: "Lab View", nivel: "Medio" }
          ]
        },
        {
          titulo: "INFORMATICA",
          dato: [
            { nombre: "Javascript", nivel: "Medio-Alto" },
            { nombre: "Vue.js", nivel: "Medio-Alto" },
            { nombre: "Node.js", nivel: "Medio-Alto" },
            { nombre: "C (lib. Arduino)", nivel: "Medio-Alto" },
            { nombre: "Assembler", nivel: "Medio-Alto" },
            { nombre: "Mongodb", nivel: "Medio" },
            { nombre: "C", nivel: "Medio" },
            { nombre: "GIT", nivel: "Medio" },
            { nombre: "Python", nivel: "Medio" },
            { nombre: "PHP", nivel: "Medio" },
            { nombre: "Linux", nivel: "Medio" },
            { nombre: "GIT", nivel: "Medio" },
            { nombre: "POO", nivel: "bajo" }
          ]
        },
        {
          titulo: "OTROS",
          dato: [
            { nombre: "Hosting && Dominio", nivel: "Medio-Alto" },
            { nombre: "Electrónca", nivel: "Medio-Alto" },
            { nombre: "Diseño 2D", nivel: "Medio-Alto" },
            { nombre: "Diseño 3D", nivel: "Medio-Alto" },
            { nombre: "Redes Conmutadas", nivel: "Medio" },
            { nombre: "Edición de Video", nivel: "Medio" }
          ]
        }
      ]
    };
  }
};
</script>
<style>
.box {
  background-color: rgb(76, 175, 80);
  border-bottom: 3px solid black;
  color: white;
  font-size: 18px;
  font-weight: bold;
}
</style>
