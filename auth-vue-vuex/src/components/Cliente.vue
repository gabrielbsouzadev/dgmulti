<template>
  <div class="col-3">
    <div class="card shadow">
      <div class="card-body">
        <h5 class="card-title">{{ cliente.nome }}</h5>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['cliente']
}
</script>