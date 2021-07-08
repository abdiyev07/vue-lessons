<template>
  <div class="user">
    <p>Доброе пожаловать {{ user.first_name }} {{ user.last_name }}</p>
  </div>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true,
      default: () => ({
        first_name: 'Неизвестный',
        last_name: 'Неизвестный',
      }),
    },
  },
}
</script>
