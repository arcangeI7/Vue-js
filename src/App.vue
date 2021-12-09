<template>
  <div class="container-fluid"> 
    <div class="row">
     <div class="col-md-4 col-lg-4 col-xl-4"> 
        <div class="card">
           <div class="card-header">          
               <button id="mostra" class=" btn-block btn-dark" data-toggle="collapse" data-target="#task" aria-expanded="false" aria-controls="task"> <h1> Task list</h1>  </button>
           </div>
           <div id="task" class="card-body collapse">
             <card></card>
           </div>
        </div>
     </div>


     <div class="col-md-4 col-lg-4 col-xl-4">
        <div class="card">
           <div class="card-header">
               <button id="mostra" class=" btn-block btn-dark" data-toggle="collapse" data-target="#task2" aria-expanded="false" aria-controls="task2"> <h1> Home task list</h1>  </button>
           </div>
           <div id="task2" class="card-body collapse">
             <card></card>
           </div>
        </div>
     </div>

     <div class="col-md-4 col-lg-4 col-xl-4">
        <div class="card">
         
       <div class="card-header">
               <button id="mostra" class=" btn-block btn-dark" data-toggle="collapse" data-target="#task3" aria-expanded="false" aria-controls="task3"> <h1> Home task list</h1>  </button>
          
       </div>

          <div id="task3" class="card-body collapse">
             <card></card>
          </div>
        </div>
     </div>
  </div>
</div>
</template>

<script>
import Card from './Card';


export default {
  name: 'app',
  components: {
    Card,
    
  },

};
</script>
<style>
div.separ {
    display: table-cell;
    padding: 15px;

}


 .separador {
    height: 100%;
    width:33%;

    margin-top: 5ps;

}
</style>
