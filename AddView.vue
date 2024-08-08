<template>
  <div>
    <h1>Add New Contact</h1>
    <AddForm />
  </div>
</template>

<script>
import AddForm from '../components/AddForm.vue';

export default {
  name: 'AddView',
  components: {
    AddForm,
  },
};
</script>
