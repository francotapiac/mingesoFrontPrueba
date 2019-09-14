<template>
  <div>
    <b-container>
      <b-card  class="col-md-12" align-self="center" bg-variant="light">

        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
          

          <b-form-group id="input-group-1" label="Nombre completo:" label-for="input-1">
            <b-form-input
              id="input-1"
              v-model="form.name"
              required
              placeholder="Juan Carlos Perez Gonzalez"
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-2" label="RUT:" label-for="input-2">
            <b-form-input
              id="input-2"
              v-model="form.rut"
              required
              placeholder="12.345.165-5"
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-3" label="Fecha de nacimiento:" label-for="input-3">
            <b-form-input
              id="input-3"
              v-model="form.date"
              required
              placeholder="16/01/1990"
            ></b-form-input>
          </b-form-group>
          

          <b-form-group id="input-group-4" label="Carreras:" label-for="input-4">
            <b-form-select
              id="input-4"
              v-model="form.career"
              :options="careers"
              required
            ></b-form-select>
          </b-form-group>


          <b-button type="submit" variant="primary">Registrar</b-button>
          <b-button type="reset" variant="danger">Reset</b-button>
        </b-form>
      </b-card> 
    </b-container> 
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          name: '',
          rut: '',
          date: '',
          career: null,
          checked: []
        },
        careers: [{ text: 'Selecciona una carrera', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
        show: true,
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>