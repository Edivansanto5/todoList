<template>
     <div class="conteiner">
        <div class="title">
            <h1>Bem-Vindo ao Gerenciamento de Tarefas</h1>
        </div>
        <br>
        <button class=" status">Status</button> 
        <input  type="text" v-model.trim="lista.text" placeholder="Digite Uma Tarefa aqui"> 
        <button type="button" @click="addLista()" class="btn"> Enviar</button>

        <div v-for="(lista, index) in listas" :key="index" class="div-main">
            
            <select class="select">
                <option >A fazer</option>
                <option >Fazendo</option>
                <option >Feito</option>
            </select>
            <span class=" span"> {{ lista.text }} </span> <a class="mr-10" @click="deleta"> 
            <i class="fa-solid fa-trash-can"></i></a>
            
                
        </div>
        <div>
            <button class="btn-1">Mostrar Atividades em Andamentos</button>
            <button class="btn2">Mostrar Atividades Concluidas</button>
        </div>

        <br>
        <br>
  </div>
</template>
<script>

export default {
    name:'todoList',
        data(){
        return{
        lista: {},
        listas: [],
        }
    },
    methods:{
        addLista(){ 
            this.listas.push(this.lista) // add um item na lista
            this.lista = {
                text: '',
            }          
        },
        deleta(){
        this.listas.pop(this.listas)
                                                                   
    
        }, 
    } 
}
</script>

<style>
    body{
        background:#383a47 ;
    }   
    .conteiner{ 
        background-color:#fff;
        text-align: center;
        max-width: 100%;
       
    }
    .title{
        color:#383a47 ;
        height: 100px;
        padding-top: 12px;
    }
    .status{
        width: 94px;
        margin: 14px;
        font-size: 18px;
        color:#383a47;
        
        
      
    }
    .btn{
        margin: 14px;
        color:#383a47 ;
        border-radius: 5px;
    }
   .div-main{
        text-align: justify;
        color: aqua;
        font-size: 20px;
        padding-left: 460px;
   } 
   a{
    color: red;
    
   }
   .select,input,.btn{
    font-size: 18px;
    margin: 4px;
   
   }
   input{
    border-radius: 5px;
   }
</style>