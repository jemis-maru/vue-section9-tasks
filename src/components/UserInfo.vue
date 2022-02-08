<template>
  <section>
    <card-style>
      <!-- <template v-slot:headerSlot> -->
      <template #headerSlot>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <template v-slot:default>
        <p>{{ infoText }}</p>
      </template>
    </card-style>
  </section>
</template>

<script>
import BaseBadge from './BaseBadge.vue';
import CardStyle from './CardStyle.vue';

export default {
  components: {
    'base-badge': BaseBadge,
    'card-style': CardStyle,
  },
  props: ['fullName', 'infoText', 'role'],
};
</script>