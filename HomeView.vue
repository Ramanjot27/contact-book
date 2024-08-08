<template>
  <div>
    <h1>Contact Manager</h1>
    <router-link to="/add" class="btn btn-primary mb-3">Add New Contact</router-link>
    <ContactList />
  </div>
</template>

<script>
import ContactList from '../components/ContactList.vue';

export default {
  name: 'HomeView',
  components: {
    ContactList,
  },
};
</script>
