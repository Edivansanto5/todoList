<template>
     <div class="conteiner">
    <h1>Bem-Vindo ao Gerenciamento de Tarefas</h1>
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
    

    
</style>