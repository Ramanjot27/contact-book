<template>
  <div>
    <h1>Contact Details</h1>
    <ContactCard :id="$route.params.id" />
  </div>
</template>

<script>
import ContactCard from '../components/ContactCard.vue';

export default {
  name: 'DetailsView',
  components: {
    ContactCard,
  },
};
</script>
