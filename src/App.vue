<template>
  <section> 
    <cabecalho :valor="titulo"/>
    <div class="container">
      
      <adicionar-tarefa v-on:adicionarTarefa="adicionarTarefa" />
      <listar-tarefas :tarefas="tarefas"/>
      <em>Altere aqui o título de sua lista de tarefas</em>
      <entrada-dados v-model="titulo"/>
    
    </div>
    <rodape />
  </section>
</template>

<script>
import Cabecalho from './components/Cabecalho';
import Rodape from './components/Rodape';
import ListarTarefas from './components/ListarTarefas';
import AdicionarTarefa from './components/AdicionarTarefa';
import EntradaDados from '@/components/templates/EntradaDados';

export default {
  name: "App",
  components: { Cabecalho, Rodape, ListarTarefas, AdicionarTarefa, EntradaDados },
  data() {
    return {
      titulo: "Minha Lista de Tarefas",
      tarefas: [
        {titulo: "Não, não pode ser o estudas", checked: false},
        {titulo: "É o programas", checked: true},
        {titulo: "Como pude não ver isto!? É o leitas!!", checked: false},
      ],
    };
  },
  methods: {
    adicionarTarefa(novaTarefa) {
      this.tarefas.push({
        titulo: novaTarefa,
        checked: false,
      });
    },
  },
};
</script>

<style>
.container{
  width: 80%;
  margin: 20px auto 0px auto;
}
ul li{
  list-style: none;
}
.removed{
  color: gray;
}

.removed label{
  text-decoration: line-through;
}
</style>
