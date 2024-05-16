<template>
  <div class="formInteractivo">

    <div class="row container g-2">
      <div class="col-12 col-md-5" id="ingresoDatos">
        <form id="formularioCurso">
          <div class="form-floating mb-3">
            <p>* Completa los campos del formulario para visualizar la información en pantalla.</p>
          </div>
          <div class="form-floating mb-3">
            <input type="text" class="form-control" id="tituloTexto" placeholder="Escriba..." v-model="curso.titulo" />
            <label for="tituloTexto">Título:</label>
          </div>
          <hr>
          <div class="form-floating mb-3">

            <select class="form-select" id="emojiTexto" v-model="curso.emoji">
              <option value="👩🏻‍💻">👩🏻‍💻</option>
              <option value="👨🏻‍💻">👨🏻‍💻</option>
              <option value="☠️">☠️</option>
            </select>
            <label for="emojiTexto">Emoji:</label>
          </div>


          <hr>

          <div class="col-md">
            <div class="form-floating mb-3 mt-3">
              <p>Apreciación: </p>
            </div>
            <div class="form-floating mb-3 d-flex">
              <div class="form-check px-3">
                <input class="form-check-input" type="radio" id="radio1" value="Regular" v-model="curso.apreciacion" />
                <label class="form-check-label" for="radio1"> Regular </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="radio" id="radio2" value="Bien" v-model="curso.apreciacion" />
                <label class="form-check-label" for="radio2"> Bien </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="radio" id="radio3" value="Muy bien" v-model="curso.apreciacion" />
                <label class="form-check-label" for="radio3"> Muy bien </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="radio" id="radio4" value="Increíble"
                  v-model="curso.apreciacion" />
                <label class="form-check-label" for="radio4"> Increíble </label>
              </div>
            </div>
          </div>


          <hr>


          <div class="col-md">
            <div class="form-floating mb-3 mt-3">
              <p>Competencias aprendidas:</p>
            </div>
            <div class="form-floating mb-3 d-flex">
              <div class="form-check px-3">
                <input class="form-check-input" type="checkbox" id="check1" value="Morfología de un componente"
                  v-model="curso.competencias" />
                <label class="form-check-label" for="check1"> Morfología de un componente </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="checkbox" id="check2" value="One-Way y Two-Way data binding"
                  v-model="curso.competencias" />
                <label class="form-check-label" for="check2"> One-Way y Two-Way data binding </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="checkbox" id="check3" value="El patrón de diseño MVVM"
                  v-model="curso.competencias" />
                <label class="form-check-label" for="check3"> El patrón de diseño MVVM </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="checkbox" id="check3" value="Directivas"
                  v-model="curso.competencias" />
                <label class="form-check-label" for="check3"> Directivas </label>
              </div>
              <div class="form-check px-3">
                <input class="form-check-input" type="checkbox" id="check3" value="Estado"
                  v-model="curso.competencias" />
                <label class="form-check-label" for="check3"> Estado </label>
              </div>
            </div>
          </div>

          <hr>
          <div class="form-floating mb-3">
            <textarea class="form-control" placeholder="" id="opinionTexto" style="height: 100px"
              v-model="curso.opinion"></textarea>
            <label for="opinionTexto">Opinión:</label>
          </div>
        </form>
      </div>
      <div class="col-12 col-md-7 text-center" id="vistaDatos">
        <span>{{ curso.emoji }}</span>
        <h1 id="tituloTexto">{{ curso.titulo }}</h1>
        <h2>Y me parece <strong>{{ curso.apreciacion }}</strong></h2>
        <p>He aprendido:</p>
        <span v-for="(competencia, index) in curso.competencias" :key="index">{{ competencia }}</span>
        <p>Mi opinión hasta ahora acerca del framework es:</p>
        <span id="opinionTexto">{{ curso.opinion }}</span>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'formInteractivo',
  data() {
    return {
      curso: {
        titulo: " ",
        emoji: " ",
        apreciacion: " ",
        competencias: [],
        opinion: " ",
      },
    };
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  margin: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}

.formInteractivo {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: center;
  font-size: 13px;
}

#ingresoDatos,
#vistaDatos {
  border-radius: 15px;
  padding: 25px;
}

#ingresoDatos {
  background-color: #333333;
  color: white;
}

#vistaDatos {
  background-color: white;
  color: black;
  align-content: center;
}

#tituloTexto,
#opinionTexto {
  text-transform: capitalize;
}
</style>
