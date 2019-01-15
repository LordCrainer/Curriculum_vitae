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
                <v-flex xs8>
                  <v-flex>
                    <v-layout row>
                      <v-flex xs4>
                        <v-card-text class="text-xs-left pa-2"
                          ><strong>NOMBRE:</strong></v-card-text
                        >
                      </v-flex>
                      <v-flex xs8>
                        <v-card-text class="text-xs-left pa-2">
                          {{ datosPersonales.Nombre }}
                          {{ datosPersonales.Apellido }}
                        </v-card-text>
                      </v-flex>
                    </v-layout>
                    <v-layout row>
                      <v-flex xs4>
                        <v-card-text class="text-xs-left pa-2"
                          ><strong>CÉDULA:</strong></v-card-text
                        >
                      </v-flex>
                      <v-flex xs8>
                        <v-card-text class="text-xs-left pa-2">
                          {{ datosPersonales.Cedula }}
                        </v-card-text>
                      </v-flex>
                    </v-layout>
                    <v-card-text class="text-xs-left pa-2">
                      <strong>Cédula:</strong> {{ datosPersonales.Cedula }}
                    </v-card-text></v-flex
                  >
                  <v-card-text class="text-xs-left pa-2">
                    <strong>Fecha:</strong>
                    {{ datosPersonales.Fecha_Nacimiento }}
                  </v-card-text>
                  <v-card-text class="text-xs-left pa-2">
                    <strong>Celular:</strong> {{ datosPersonales.Celular }}
                  </v-card-text>
                  <v-card-text class="text-xs-left pa-2">
                    <strong>Correo: </strong>{{ datosPersonales.Email }}
                  </v-card-text>
                  <v-card-text class="text-xs-left pa-2">
                    <strong>Correo2:</strong> {{ datosPersonales.Email2 }}
                  </v-card-text>
                  <v-card-text class="text-xs-left pa-2">
                    <strong>Teléfono:</strong> {{ datosPersonales.Telefono }}
                  </v-card-text>
                  <v-card-text class="text-xs-left pa-2">
                    <strong>Dirección:</strong> {{ datosPersonales.Direccion }}
                  </v-card-text>
                </v-flex>
                <v-flex>
                  <v-img
                    height="150"
                    width="100"
                    src="https://uploads.codesandbox.io/uploads/user/17fffd86-3ee1-4ca9-abc0-4e76a2cb57f0/dfNi-img.jpg"
                    aspect-ratio="0.75"
                  ></v-img>
                </v-flex>
              </v-layout>
            </v-container>
          </v-card-text>
        </v-card>
      </v-flex>
      <v-flex>
        <TimeCard :data="formacionAcademica" tema="FORMACIÓN ACADÉMICA">
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
        <TimeCard :data="experienciaLaboral" tema="EXPERIENCIA LABORAL">
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
        <v-card>
          <v-card-text class="box "> CONOCIMIENTOS </v-card-text>
        </v-card>
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
        { nombre: "caangarc@espol.edu.ec", titulo: "EMAIL (SECUNDARIO)" },
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
            "Cursando Noveno Semestre de la carrera Ingenería Electrónica y Telecomunicaciones en la Espol"
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
          descripcion: "Diseñador Gráfico tanto 2D como 3D"
        },
        {
          inicio: 2015,
          fin: 2018,
          descripcion:
            "Instalación y Configuración de equipos asociados al área de las telecomunicaciones y la seguridad, como antenas y cámaras de seguridad"
        },
        {
          inicio: 2015,
          fin: 2019,
          descripcion:
            "Desarrollador de Hardware usando PIC, Arduino y Raspberry Pi"
        },
        {
          inicio: 2015,
          fin: 2019,
          descripcion:
            "Desarrollador de páginas web mediante el stack MEVN (Mongodb, Express.js, Vue.js y Node.js)"
        }
      ],
      conocimientos: [
        {
          IDIOMA: [
            { nivel: "medio-alto", nombre: "Inglés" },
            { nivel: "alto", nombre: "Español" }
          ]
        },
        {
          PROGRAMAS: [
            { nombre: "Photoshop", nivel: "medio" },
            { nombre: "Illustrator", nivel: "medio" },
            { nombre: "Sketchup", nivel: "medio-alto" },
            { nombre: "Word", nivel: "medio-alto" },
            { nombre: "Power Point", nivel: "alto" },
            { nombre: "Excel", nivel: "medio-alto" },
            { nombre: "Proteus", nivel: "medio-alto" },
            { nombre: "Ansys Electronic", nivel: "medio" },
            { nombre: "Lab View", nivel: "medio" }
          ]
        },
        {
          INFORMATICA: [
            { nombre: "Javascript", nivel: "medio-alto" },
            { nombre: "Node.js", nivel: "medio-alto" },
            { nombre: "Vue.js", nivel: "medio-alto" },
            { nombre: "C (lib. Arduino)", nivel: "medio-alto" },
            { nombre: "Assembler", nivel: "medio-alto" },
            { nombre: "Mongodb", nivel: "medio" },
            { nombre: "C", nivel: "medio" },
            { nombre: "GIT", nivel: "medio" },
            { nombre: "Python", nivel: "medio" },
            { nombre: "PHP", nivel: "medio" },
            { nombre: "Linux", nivel: "medio" },
            { nombre: "GIT", nivel: "medio" },
            { nombre: "POO", nivel: "bajo" }
          ]
        },
        {
          OTROS_CONOC: [
            { nombre: "Hosting && Dominio", nivel: "medio-alto" },
            { nombre: "Electrónca", nivel: "medio-alto" },
            { nombre: "Diseño 2D", nivel: "medio-alto" },
            { nombre: "Diseño 3D", nivel: "medio-alto" },
            { nombre: "Redes Conmutadas", nivel: "medio" },
            { nombre: "Edición de Video", nivel: "medio" }
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
  border: 1px solid red;
  color: white;
  font-size: 18px;
  font-weight: bold;
}
</style>
