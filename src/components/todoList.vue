<template>
     <div class="conteiner">
        <div class="title">
            <h1>Bem-Vindo ao Gerenciamento de Tarefas</h1>
        </div>
        <br><br>
        <button class=" status">Status</button> 
        <input  type="text" v-model.trim="lista.text" placeholder="Digite Uma Tarefa aqui"> 
        <button type="button" @click="addLista()" class="btn"> Enviar</button>

        <div v-for="(lista, index) in listas" :key="index" class="div-main">
            
            <select>
                <option >A fazer</option>
                <option >Fazendo</option>
                <option >Feito</option>
            </select>
            <span class=" span"> {{ lista.text }}</span> <a class="mr-10" @click="deleta"> <i class="fa-solid fa-trash-can"></i></a>
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
        background-color: aqua;
    }   
    .conteiner{ 
        background-color: pink;
        text-align: center;
        width: 50%;
        height:50%;
    }
    .title{
        background: green;
        height: 100px;
        padding-top: 12px;
    }
    .status{
        width: 60px;
        margin: 14px;
    }
    .btn{
        
        margin: 14px;
        
    }
   .div-main{
    text-align: justify;
    background: rgb(128, 0, 75);
    padding-left: 140px;
   
   
   }
</style>