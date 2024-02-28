<script lang="ts">
export default {
  data() {
    return {
      items: ["Шаблон", "Группировки", "Показатели", "Название и доступ"],
    };
  },
};
</script>

<template>
  <v-stepper editable v-slot:default="{ prev, next }">
    <v-stepper-header>
      <template v-for="(item, id) in items" :key="id">
        <v-stepper-item
          edit-icon=""
          :value="id + 1"
          :title="item"
        ></v-stepper-item>
        <v-divider v-if="id < items.length - 1"></v-divider>
      </template>
    </v-stepper-header>
    <v-stepper-window>
      <v-stepper-window-item
        v-for="(item, id) in items"
        :key="id"
        :value="id + 1"
      >
      <template>
        <v-card :title="`step ${item}`"></v-card>
      </template>
      </v-stepper-window-item>
    </v-stepper-window>
    <v-stepper-actions
      next-text="Продолжить"
      @click:next="next"
      prev-text="Отменить"
      @click:prev="prev"
    ></v-stepper-actions>
  </v-stepper>
</template>
