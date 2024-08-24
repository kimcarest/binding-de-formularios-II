<template>
  <div class="wrapper">
    <div class="wrapper__form">
        <div class="campo">
          <label for="titulo">Titulo:</label>
          <input v-model="titulo" type="text" name="titulo" id="titulo">
        </div>

        <div class="campo">
          <label for="emoji">Emoji:</label>
          <select v-model="emoji" name="emoji" id="emoji">
            <option value="👨‍💻">👨‍💻</option>
            <option value="🗽">🗽</option>
            <option value="😄">😄</option>
          </select>
        </div>

        <div class="campo">
          <p class="campo__title">Apreciación:</p>

          <div class="campo__radio">
            <input v-model="apreciacion" type="radio" name="apreciacion" id="regular" value="Regular">
            <label for="regular">Regular</label>
          </div>
          
          <div class="campo__radio">
            <input v-model="apreciacion" type="radio" name="apreciacion" id="bien" value="Bien">
            <label for="bien">Bien</label>
          </div>

          <div class="campo__radio">
            <input v-model="apreciacion" type="radio" name="apreciacion" id="muyBien" value="Muy bien">
            <label for="muyBien">Muy bien</label>
          </div>

          <div class="campo__radio">
            <input v-model="apreciacion" type="radio" name="apreciacion" id="increible" value="Increible">
            <label for="increible">Increible</label>
          </div>
        </div>

        <div class="campo campo--competencias">
          <p class="campo__title">Competencias aprendidas:</p>

            <div class="campo__checkbox">
              <div>
                <input v-model="competencias" type="checkbox" name="morfologia" id="morfologia" value="Morfología de un componente">
                <label for="morfologia">Morfología de un componente</label>
              </div>

              <div>
                <input v-model="competencias" type="checkbox" name="oneWay" id="oneWay" value="One-Way y Two-Way data binding">
                <label for="oneWay">One-Way y Two-Way data binding</label>
              </div>

              <div>
                <input v-model="competencias" type="checkbox" name="patron" id="patron" value="El patrón de diseño MVVM">
                <label for="patron">El patrón de diseño MVVM</label>
              </div>
            </div>

            <div class="campo__checkbox">
              <div>
                <input v-model="competencias" type="checkbox" name="estado" id="estado" value="Estado">
                <label for="estado">Estado</label>
              </div>

              <div>
                <input v-model="competencias" type="checkbox" name="directivas" id="directivas" value="Directivas">
                <label for="directivas">Directivas</label>
              </div>
            </div>
        </div>

        <div class="campo">
          <label for="opinion">Opinión</label>
          <textarea v-model="opinion" name="opinion" id="opinion"></textarea>
        </div>
    </div>
    <div class="wrapper__display">
      <h1>{{ emoji }}</h1>

      <h2>{{ titulo }}</h2>

      <strong>Y me parece {{ apreciacion }}</strong>
      <br>
      <br>
      <strong>He aprendido:</strong>
      <br>
      <br>
      <strong>{{ competencias }}</strong>
      <br>
      <br>
      <strong>Mi opinión hasta ahora del framework es:</strong>

      <p>{{ opinion }}</p>
    </div>
  </div>
</template>



<script setup>
  import { ref } from 'vue'
  const titulo = ref('Estoy aprendiendo Vue')
  const emoji = ref('👨‍💻')
  const apreciacion = ref('Increible')
  const competencias = ref([ "Morfología de un componente", "Directivas", "Estado", "One-Way y Two-Way data binding", "El patrón de diseño MVVM" ])
  const opinion = ref('Ahora podré desarrollar aplicaciones más cómodamente!!')
</script>

<style>
  .wrapper {
    display: flex;
    gap: .5rem;
  }
  .wrapper__form {
    padding: 2rem;
    border-radius: 1rem;
    color: #FFF;
    background: #000;
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
  .wrapper__display {
    padding: 2rem;
    border-radius: 1rem;
    border: 2px solid gray;
    flex: 2;
    width: 100%;
  }
  .campo {
    display: flex;
    align-items: center;
    gap: .5rem;
  }

  .campo--competencias {
    display: flex;
    align-items: start;
    gap: 2rem;
  }

  .campo__checkbox {
    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 1rem;
  }

  .campo__checkbox div {
    display: flex;
    gap: .5rem;
    align-items: start;
    text-align: start;
  }

  .campo__title {
    margin: 0;
  }

  select,
  input {
    padding: .2rem;
  }

  textarea {
    width: 100%;
  }

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>