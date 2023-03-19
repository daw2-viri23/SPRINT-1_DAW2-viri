
<template>
    <div>
      <main> 
          <div v-if="$route.params.id > 0">
              <div class="" v-for="item in Alumnos" :key="item.id">
                      <div v-if="item.id == $route.params.id">
                          <DetalleAlumno :persona="item"/>
                      </div>
              </div>
              <div class="" v-for="item in Profesores" :key="item.id">
                      <div v-if="item.id == $route.params.id">
                          <DetalleAlumno :persona="item"/>
                      </div>
              </div>
          </div>
          <div v-else>
            
              <div class="container-fluid">
              <div class="bg-success">
                  <div class="row p-0">
                      <h1 class="pt-4 pb-5 text-center fs-1">Profesores</h1>
                      <div class="d-flex justify-content-center">
                          <div v-for="item in Profesores" :key="item.id">
                              <fichaProfesor v-if="item.tipo == 'profesor'" :persona="item"/>
                          </div>
                      </div>
                      <h1 class="pt-5 pb-5 text-center fs-1">Alumnos</h1>
                      <div class="d-flex justify-content-center pb-5">
                          <div v-for="item in Alumnos" :key="item.id">
                              <div v-if="item.tipo == 'alumno'">
                                  <fichaAlumno :persona="item"/>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
            </div>
          </div>
      </main> 
    </div>
</template>

<script>
import fichaProfesor from '../components/fichaProfesor.vue'
import fichaAlumno from '../components/fichaAlumno.vue'
import DetalleAlumno from '../components/DescripcionPersona.vue';

export default {
    name: 'Anuario',
    components:{
    fichaAlumno,
    fichaProfesor,
    DetalleAlumno
},
    // Los datos son las variables
    data(){
        return{
            Profesores: [
            {
                    id:3,
                    nombre: 'Jordi Egea',
                    photo: 'profesor1.png',
                    tipo: 'profesor'
                },
                {
                    id:1,
                    nombre: 'Carlos Arrebola',
                    photo: 'profesor.png',
                    tipo: 'profesor'
                },
                {
                    id:2,
                    nombre: 'Patricia Salinas',
                    photo: 'profesor3.jpg',
                    tipo: 'profesor'
                },
                
            ],
            Alumnos: [
                {
                    id:6,
                    nombre: 'José Luis Viri',
                    photo: 'joseluisviri.jpeg',
                    tipo: 'alumno',
                    estudios:['Grado medio en Sistemas Microinformáticos y Redes'],
                    trabajo:['Desempleado']
                },
                {
                    id:7,
                    nombre: 'Frank Cesc',
                    photo: 'frank.jpeg',
                    tipo: 'alumno',
                    estudios:['Grado medio en Sistemas Microinformáticos y Redes'],
                    trabajo:['Desempleado']
                },
                {
                    id:8,
                    nombre: 'Marcos García',
                    photo: 'marcos.jpeg',
                    tipo: 'alumno',
                    estudios:['Grado medio en Sistemas Microinformáticos y Redes'],
                    trabajo:['Asistente de cajas en Carrefour']
                },
            ]
        }
    }
}
</script>

<style>
*{
    padding: 0;
    margin: 0;
}

</style>