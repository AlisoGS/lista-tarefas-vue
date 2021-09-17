<template>
  <div class="input-group">
        <!--<input @keyup.enter="adicionarTarefa()" v-model="novaTarefa" type="text"> -->
        <!-- <entrada-dados :value="novaTarefa" @input="associarValor" @salvar="adicionarTarefa"/> -->
        <entrada-dados v-model="novaTarefa" @salvar="adicionarTarefa"/>
        <span class="input-group-btn">
          <button @click="adicionarTarefa()" class="btn btn-primary">
            Adicionar Tarefa
          </button>
        </span>
      </div>
</template>

<script>
import EntradaDados from '@/components/templates/EntradaDados';
export default {
    components: { EntradaDados },
    data(){
        return{
            novaTarefa: "",
        };
    },
    methods: {
        adicionarTarefa(){
            this.$emit("adicionarTarefa", this.novaTarefa)
            this.novaTarefa = "";
            this.$forceUpdate()
        },
        associarValor(valor){
            this.novaTarefa = valor;
        },
    }
};
</script>

<style>
</style>