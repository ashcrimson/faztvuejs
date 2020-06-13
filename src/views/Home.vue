<template>
  <div class="home">
    <h1>Hola mundo</h1>
    <!--<Test msg="HOLA!!!"/>-->
    <User/>
  </div>
</template>

<script>
import Test from '@/components/Test.vue';
import User from '@/components/User.vue';
export default {
  name: 'Home',
  components: {
    Test,
    User
  }
}
</script>
