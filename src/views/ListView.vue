<template>
  <div>
    <h1>Lista de Peleadores</h1>
    <br><br>
    <div class="row d-flex justify-content-center">
      <div class="col-2" v-for="peleador in peleadores"
        :key="peleador.id"
        @click="getPeleadores(peleador.id)">
        <div class="card" >
      <img :src="peleador.imgSrc" class="card-img-top" alt="...">
      <div class="card-body">
        <h6 class="card-title pointer">{{ peleador.nombre }}</h6>
        <p class="card-text">{{ peleador.id }}</p>
      </div>
    </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    peleadores: [],
  }),
  created() {
    fetch("/peleadores.json")
      .then((res) => res.json())
      .then((data) => {
        this.peleadores = data;
      });
  },
  methods: {
    getPeleadores(id) {
      this.$router.push(`/list/${id}`);
    },
  },
};
</script>

<style>
.card-img-top{
  max-height:200px;
}
.pointer{
  cursor: pointer;
}
</style>