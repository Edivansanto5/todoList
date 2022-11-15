<template>
     <div class="conteiner">
    <h3>Digite um item</h3>
    <input type="text" v-model.trim="lista.text" placeholder="Digite Qualque coisa"> <!-- ok-->
    <button type="button" @click="addLista()" > Enviar</button>

    <div v-for="(lista, index) in listas" :key="index" >
        <span>{{ lista.text }}</span> <a class="mr-10" href="#" @click="deleta">Excluir</a>
        
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
        console.log('veio parar aqui');                                                            
    
        }, 
    } 
}
</script>

<style>
    

    
</style>