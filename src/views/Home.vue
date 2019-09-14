<template>
  <div class="home">

    <RegisterStudentForm/>
  
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import RegisterStudentForm from '@/components/RegisterStudentForm.vue'

export default {
  name: 'home',
  components: {
    HelloWorld,
    RegisterStudentForm
  }
}
</script>
