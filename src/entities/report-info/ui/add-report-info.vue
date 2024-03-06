<template>
  <div class="d-flex align-center justify-center">
    <v-btn v-if="!dialog" @click="dialog = !dialog">
      <v-icon icon="mdi-view-dashboard" size="large" start /> Создать отчёт
    </v-btn>
  </div>
  <v-container v-if="dialog" style="border: 1px solid #e0e0e0" class="rounded">
    <v-chip size="x-large" variant="text" style="font-weight: bold">
      <v-icon
        icon="mdi-file-chart-outline"
        color="blue-lighten-1"
        class="mr-1"
      ></v-icon>
      Создание нового отчета
    </v-chip>
    <v-stepper editable v-model="step">
      <v-stepper-header>
        <template v-for="(item, id) in items" :key="id">
          <v-stepper-item
            edit-icon=""
            :value="id + 1"
            :title="item"
          ></v-stepper-item>
          <v-divider v-if="id + 1 < items.length"></v-divider>
        </template>
      </v-stepper-header>
      <v-stepper-window v-model="step">
        <v-stepper-window-item :value="1">
          <v-card
            >Выберите один из шаблонов для будущего отчёта. Шаблоны отличаются
            настройками группировок и показателей. Выбранный шаблон можно
            изменить на следующих шагах создания отчёта.
            <v-card-text>{{ response.name }}</v-card-text>
          </v-card>
        </v-stepper-window-item>

        <v-stepper-window-item :value="2">
          <v-card
            >Группировка отвечает за то, какие строки будут видны в вашем
            отчёте. Вы можете построить отчёт в разрезе источников визитов
            (например, рекламных каналов) или по доменам. Подробнее о
            группировках читайте в документации.
            <v-card-text>{{ response.order_nesting }}</v-card-text>
            <v-card-text>{{ response.nesting }}</v-card-text>
          </v-card>
        </v-stepper-window-item>

        <v-stepper-window-item :value="3">
          <v-card
            >Вы можете настроить таблицу так, чтобы она содержала только нужные
            вам показатели. Подробно узнать о показателе можно во всплывающей
            подсказке.
            <v-card-text>{{ response.fields }}</v-card-text>
          </v-card>
        </v-stepper-window-item>

        <v-stepper-window-item :value="4">
          <v-card>
            <v-card-text> </v-card-text>
          </v-card>
        </v-stepper-window-item>
      </v-stepper-window>

      <v-divider></v-divider>

      <v-card-actions>
        <v-btn
          :style="step > 3 ? '' : 'border: 1px solid #bdbdbd'"
          class="text-none"
          color="blue-lighten-1"
          :variant="step > 3 ? 'flat' : 'outlined'"
          @click="step > 3 ? (dialog = !dialog) : step++"
        >
          {{ step > 3 ? "Сохранить отчёт" : "Продолжить" }}
        </v-btn>
        <v-btn
          style="border: 1px solid #bdbdbd"
          class="text-none"
          color="blue-lighten-1"
          @click="dialog = !dialog"
          >Отменить</v-btn
        >
      </v-card-actions>
    </v-stepper>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    const items = ["Шаблон", "Группировки", "Показатели", "Название и доступ"];
    const step = 1;
    const dialog = false;
    const response = {
      fields: ["", ""],
      order_nesting: [[1]],
      nesting: [
        {
          value: 1,
          header: "Канал",
        },
      ],
      name: "По каналам",
      type: 1,
    };

    return { items, step, dialog, response };
  },
});
</script>
