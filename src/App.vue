<template>
  <div id="app">
    <Header :nome="nome" />
    <main class="content">
      <div class="row">
        <input type="text" v-model="novaTarefa">
        <button @click.prevent="adicionarTarefa">Adicionar</button>
      </div>
      <div class="tasks">
        <ul>
          <li v-for="(tarefa, index) of tarefas" :key="index">
            <input type="checkbox" v-model="tarefa.checked">
            <span :class="{ riscado: tarefa.checked }">{{ tarefa.nome }}</span>
          </li>
        </ul>
        <input type="text" v-model="nome" placeholder="Altere aqui seu nome">
      </div>
      <Footer />
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components: {Header, Footer},
  data() {
    return {
      novaTarefa: '',
      tarefas: [],
      nome: ''
    }
  }, methods: {
    adicionarTarefa() {
      if (this.novaTarefa != '') {
        this.tarefas.push({
        nome: this.novaTarefa,
        checked: false
        })
        this.novaTarefa = ''
      }
    }
  }
}
</script>

<style>
.content {
  display: flex;
  flex-flow: column;
  align-items: center;
  padding: 30px 0;
}
.row input{
  width: 300px;
}
.tasks ul{
  margin: 30px 0;
}
.riscado {
  color: gray;
  text-decoration: line-through;
}
</style>
