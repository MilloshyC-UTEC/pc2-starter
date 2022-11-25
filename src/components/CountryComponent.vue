<script>
export default {
  name: "CountryComponent",
  props: [
    "name",
    "capital",
    "currency_name",
    "currency",
    "region",
    "code",
    "iso2"
    
  ],
  HacerClick: false, //: crear una propiedad para determinar si al componente se le puede hacer click
};
</script>

<template>
  <!-- Utilizar la propiedad creada para controlar el click. Cuando el componente es "clickeable", redirigir a la pagina del pais.
  Mira las rutas para ver como redirigir al usuario.-->
  <h1 v-if="HacerClick===true">/countries/:code</h1>
  <div class="country country-hover"
  >
  <!-- Poblar el HTML con las propiedades. Usar https://countryflagsapi.com/png/${code}-->
  <img
      width="200"
      height="200"
      src="https://countryflagsapi.com/png/{{code}}"
    />
    <h1> {{name}}</h1>
    <h2>Capital: {{capital}}</h2>
    <h3>Moneda: {{currency_name}}</h3>
    <h3>Region: {{region}}</h3>
  </div>
</template>

<style scoped>
.country {
  padding: 2px;
  white-space: nowrap;
  width: 350px;
  height: 350px;
  border-style: solid;
  border-radius: 5px;
  border-color: grey;
}

.country-hover:hover {
  background-color: rgb(49, 49, 49);
  cursor: pointer;
}

h1 {
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
