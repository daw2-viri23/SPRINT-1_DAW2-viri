<template>
    <div class="row bg-success ">
              <div class="col-12 d-flex justify-content-center bg-success">
                <div class="card mt-5 w-15">
                  <img class="imagenCard imagenDetalle" :src='"/public/img/"+persona.photo' alt="Card image cap">
                  <div class="card-body h-40">
                    <div class="row">
                      <div class="col-6">
                        <h5 class="card-title pe-3">{{persona.nombre}}</h5>
                      </div>
                      <div class="col-6">
                        <h5 class="card-title">Estudiante</h5>
                        <h5 class="card-title">Curso 2022-2023</h5>
                        <i class="fa-sharp fa-solid fa-briefcase pe-2"></i>
                        <i class="fa-solid fa-magnifying-glass col-12"></i>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div> 
            <div class="row bg-success espacioExpediente">
              <div class="col-12">
                <div class="accordion pt-5 pe-5 ps-5" id="accordionExample">
                  <div class="accordion-item">
                    <h2 class="accordion-header bg-secondary text-white d-flex justify-content-center" id="flush-headingOne">EXPEDIENTE DEL ALUMNO</h2>

                      <div class="accordion-body bg-primary">
                        <div class="row">
                            <div class="col-6">
                                <h2 class="pt-2 pb-2">Formacion:</h2>
                                <div class="" v-for="item in persona.estudios" :key="item.id">
                                    <ul>
                                        <li>{{item}}</li>
                                    </ul>
                                </div>
                            </div>
                            <div class="col-6">
                                <h2 class="pt-2 pb-2">Experiencia laboral</h2>
                                <div class="" v-for="item in persona.trabajo" :key="item.id">
                                    <ul>
                                        <li>{{item}}</li>
                                    </ul>
                                </div>  
                            </div>
                        </div>
                      </div>

                  </div>
                </div>
              </div>
    </div>
    
</template>
    
<script>
    export default {
        name: 'TheCard',
        //Props es para recibir variables, en este caso le dicimos que va a recibir una variable.
        //Recibira la array de ListaAlumnos y se guardara. Tenemos que decirle que tipo es
        props: {
            persona: Object
        }
    }
</script>
    
    <style>
    
    </style>