<template>
  <div class="card">
    <div class="card-body quote">
      <p class="card-text">
        "<slot></slot>"
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Quote",
    props: ['quote']
  }
</script>

<style scoped>
  .card:hover {
    background-color: lightcoral;
    cursor: pointer;
  }

  .card{
    display: inline-block;
    margin: 5px;
    min-width: 200px;
    max-width: 500px;
  }
  .card-body {
    min-width: 200px;
    max-width: 500px;
    padding: 5px;
    font-size: 24px;
    font-family: 'Arizonia', cursive;
  }
</style>
