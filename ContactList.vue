<template>
    <div class="row">
      <input v-model="searchQuery" class="form-control mb-3" placeholder="Search Contacts" />
      <div class="col-md-4" v-for="contact in filteredContacts" :key="contact.id">
        <ContactCard :contact="contact" />
      </div>
    </div>
  </template>
  
  <script>
  import ContactCard from './ContactCard.vue';
  
  export default {
    name: 'ContactList',
    components: {
      ContactCard,
    },
    data() {
      return {
        contacts: JSON.parse(localStorage.getItem('contacts') || '[]'),
        searchQuery: '',
      };
    },
    computed: {
      filteredContacts() {
        return this.contacts
          .filter(contact =>
            contact.firstName.toLowerCase().includes(this.searchQuery.toLowerCase()) ||
            contact.lastName.toLowerCase().includes(this.searchQuery.toLowerCase())
          )
          .sort((a, b) => a.lastName.localeCompare(b.lastName));
      },
    },
  };
  </script>
  