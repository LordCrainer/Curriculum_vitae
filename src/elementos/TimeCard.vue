<template>
  <v-card>
    <slot name="tema"></slot> <slot name="informacion"></slot>
    <v-card-text>
      <v-container>
        <slot name="titulo"></slot> <slot name="otro"></slot>
        <v-layout row v-for="(form, ind) in data" :key="ind">
          <v-flex xs3> <slot name="time" :item="form"></slot> </v-flex>
          <v-flex xs9> <slot name="descripcion" :item="form"></slot> </v-flex>
        </v-layout>
      </v-container>
    </v-card-text>
  </v-card>
</template>
<script>
export default {
  props: ["tema", "data"]
};
</script>
