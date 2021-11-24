<template>
  <div class="Home">
    <Form >
    </Form>
  </div>
  <p></p>
   
 
  <div class="Ticket">
    <LandingPage>
    </LandingPage>
  </div>

</template>

<script>
// @ is an alias to /src
import Form from '@/components/Form.vue'
import LandingPage from '@/components/LandingPage.vue'

export default {
  name: 'Home',
  components: {
    Form,
    LandingPage
  },
 
}
</script>
<style >
  body{
    background-color: bisque;
  }
</style>