<script lang="ts"></script>

<template>
  <v-container style="border: 1px solid red">
    <div class="mb-2">Создание нового отчета</div>

    <v-stepper
      hide-actions
      editable
      :items="['Шаблон', 'Группировки', 'Показатели', 'Название и доступ']"
    >
      <template v-slot:item.1>
        <v-card title="Step One" flat>...</v-card>
      </template>

      <template v-slot:item.2>
        <v-card title="Step Two" flat>...</v-card>
      </template>

      <template v-slot:item.3>
        <v-card title="Step Three" flat>...</v-card>
      </template>

      <template v-slot:item.4>
        <v-card title="Step Four" flat>...</v-card>
      </template>
    </v-stepper>

    <v-btn class="mt-2">Продолжить</v-btn>
    <v-btn class="mt-2 ml-4">Отменить</v-btn>
  </v-container>
</template>
