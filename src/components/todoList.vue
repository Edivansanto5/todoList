<template>
     <div class="conteiner">
        <div class="title">
            <h1>Bem-Vindo ao Gerenciamento de Tarefas</h1>
        </div>
        <br><br>
        <button>Status</button>
        <input type="text" v-model.trim="lista.text" placeholder="Digite Uma Tarefa aqui"> 
        <button type="button" @click="addLista()" > Enviar</button>

        <div v-for="(lista, index) in listas" :key="index" >
            
            <select>
                <option >A fazer</option>
                <option >Fazendo</option>
                <option >Feito</option>
            </select>
            <span> {{ lista.text }}</span> <a class="mr-10" @click="deleta"> <i class="fa-solid fa-trash-can"></i></a>
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
        width: 100%;
        height:100%;
    }
    .title{
        background: green;
        height: 100px;
        padding-top: 12px;
  
   
    }
</style>