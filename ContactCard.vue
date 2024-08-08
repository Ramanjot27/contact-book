<template>
    <div class="card mb-3">
      <div class="card-body">
        <h5 class="card-title">{{ contact.firstName }} {{ contact.lastName }}</h5>
        <p class="card-text">{{ contact.email }}</p>
        <router-link :to="{ path: '/contact/' + contact.id }" class="btn btn-primary btn-sm me-2">View</router-link>
        <router-link :to="{ path: '/edit/' + contact.id }" class="btn btn-warning btn-sm me-2">Edit</router-link>
        <button @click="deleteContact(contact.id)" class="btn btn-danger btn-sm">Delete</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ContactCard',
    props: {
      contact: Object,
      id: [String, Number]
    },
    methods: {
      deleteContact(id) {
        let contacts = JSON.parse(localStorage.getItem('contacts') || '[]');
        contacts = contacts.filter(contact => contact.id !== id);
        localStorage.setItem('contacts', JSON.stringify(contacts));
        this.$emit('update');
      },
    },
  };
  </script>
  