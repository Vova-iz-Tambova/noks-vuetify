<script lang="ts"></script>

<template>
  <v-container style="border: 1px solid #e0e0e0" class="rounded">
    <v-chip
      size="x-large"
      variant="text"
      color="grey-darken-3"
      style="font-weight: bold"
    >
      <v-icon
        icon="mdi-file-chart-outline"
        color="blue-lighten-1"
        class="mr-1"
      ></v-icon>
      Создание нового отчета
    </v-chip>

    <v-stepper flat hide-actions editable bg-color="grey-lighten-2">
      <v-stepper-header>
        <v-stepper-item edit-icon title="Шаблон" value="1"></v-stepper-item>
        <v-divider></v-divider>
        <v-stepper-item
          edit-icon
          title="Группировки"
          value="2"
        ></v-stepper-item>
        <v-divider></v-divider>
        <v-stepper-item edit-icon title="Показатели" value="3"></v-stepper-item>
        <v-divider></v-divider>
        <v-stepper-item
          edit-icon
          title="Название и доступ"
          value="4"
        ></v-stepper-item>
      </v-stepper-header>

      <v-stepper-window>
        <v-stepper-window-item value="1">
          <v-card title=" One" flat>...</v-card>
        </v-stepper-window-item>

        <v-stepper-window-item value="2">
          <v-card title=" Two" flat>...</v-card>
        </v-stepper-window-item>

        <v-stepper-window-item value="3">
          <v-card title=" Three" flat>...</v-card>
        </v-stepper-window-item>

        <v-stepper-window-item value="4">
          <v-card title=" Four" flat>...</v-card>
        </v-stepper-window-item>
      </v-stepper-window>
    </v-stepper>

    <v-btn
      style="border: 1px solid #bdbdbd"
      class="ma-3 text-none"
      color="blue-lighten-1"
      variant="outlined"
      >Продолжить</v-btn
    >
    <v-btn
      style="border: 1px solid #bdbdbd"
      class="text-none"
      color="blue-lighten-1"
      variant="outlined"
      >Отменить</v-btn
    >
  </v-container>
</template>
