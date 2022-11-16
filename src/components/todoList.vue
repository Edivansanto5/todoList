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

            <select class="select" > 
               
                <option>A fazer</option>
                <option>Fazendo</option>
                <option>Feito</option>
            </select>
            <span class="span"> {{ lista.text }} </span> <a class="mr-10" @click="deleta"> 
            <i class="fa-solid fa-trash-can"></i></a>
            
    
        </div>
        <br><br><br>

        <div>
            <button class="btn-1" @click="mostrarFazendo()">{{mostrarAndamento}}</button>
            
            <button class="btn-2" @click="mostrarFeito()">{{mostrarAndamento2}}</button>
        </div>
        <div v-if="fazendo">
            <h2>Lista de items em Andamentos</h2>
            
            <ul >
                <li>item1</li>
                <li>item2</li>
                <li>item3</li>
                <li>item4</li>
            </ul>

        </div>
        <div v-if="fazendo2">
            <h2>Lista de items Finalizados</h2>
            <ul>
                <li>item5</li>
                <li>item6</li>
                <li>item7</li>
                <li>item8</li>
            </ul>

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
            opcion:[
                {id:1, name:'A Fazer'},
                {id:2,  name:'Fazendo'},
                {id:3, name:'Feito'}
            ],
            lista: {},
            listas: [],
            fazendo:false,
            fazendo2: false,
            mostrarAndamento:'Mostrar Atividades em Andamentos',
            mostrarAndamento2:'Mostrar Atividades Finalizado'

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
        mostrarFazendo(){
            this.fazendo = !this.fazendo
            if(!this.fazendo){
                this.mostrarAndamento = 'Mostrar Atividades em Andamentos'
            }else{
                this.mostrarAndamento = 'Fechar lista Finalizados'
            }
        },
        mostrarFeito(){
            this.fazendo2 = !this.fazendo2
            if(!this.fazendo2){
                this.mostrarAndamento2 = 'Mostrar Atividades em Andamentos'
            }else{
                this.mostrarAndamento2 = 'Fechar lista em Andamentos'
            }
            
            console.log('Mostrar atividades Concluidas')
        }
      
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
    .btn-1,.btn-2{
        margin: 14px;
        color:#383a47 ;
        border-radius: 5px;
        font-size: 14px;
    }
    .div-main{
        text-align: justify;
        color: aqua;
        font-size: 20px;
        padding-left: 460px;
   } 
   a {
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