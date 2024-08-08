<template>
  <div>
    <h1>Edit Contact</h1>
    <EditForm :id="$route.params.id" />
  </div>
</template>

<script>
import EditForm from '../components/EditForm.vue';

export default {
  name: 'EditView',
  components: {
    EditForm,
  },
};
</script>
