<template>
  <div class="footer mt-3">
    <h3 class="bg-dark bg-gradient text-center text-white py-3 mb-0">
      &copy; {{ getYear }} - Gastón Martinez
    </h3>
  </div>
</template>

<script>
export default {
  computed: {
    getYear() {
      return new Date().getFullYear();
    },
  },
};
</script>

<style scoped></style>
