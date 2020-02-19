<template>
  <div id="app">

    <b-navbar type="dark" variant="success">
    <b-navbar-brand>App do Pet</b-navbar-brand>

    <b-navbar-nav>
      <b-nav-item href="#" @click="exibeListagem = false">Agendar</b-nav-item>
    </b-navbar-nav>

    </b-navbar>  


    <b-container>
      <b-row class="col-md-12">
        
        <div v-if="exibeListagem">
        
          <b-card title="Listagem de Agendamentos">
            <b-table striped hover :items="agendamentos" :fields="colunas"></b-table>
          </b-card>
        
        </div>  

        <div v-else>

          <Agendamento></Agendamento>
         

        </div>    
      </b-row>  
    </b-container>  
       
  </div>
</template>

<script>

import Agendamento from "./components/Agendamento"

export default {
  name: 'App',


  components:{Agendamento},


    data (){
      
      return{
        exibeListagem: true,
        colunas:[
          {key: "datahora", label: "Data e hora", sortable: true},
          {key: "nome", label: "Nome do Pet", sortable: true},
          {key: "servico", label: "Serviço"},
        ],
        agendamentos:[
          {"datahora":"07-11-2020 09:00", "nome":"Babi", "servico":"hidratação"},
          {"datahora":"20-10-2020 10:45", "nome":"Babi", "servico":"banho"}
        ],

        
      }

    },

    
  
  }

</script>

<style>

</style>
