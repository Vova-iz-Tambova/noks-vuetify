<script lang="ts">
export default {
  data() {
    return {
      e1: 1,
      steps: 1,
      res: {
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
      },
    };
  },

  computed: {
    disabled() {
      return this.e1 === 1
        ? "prev"
        : this.e1 === this.steps
        ? "next"
        : undefined;
    },
  },
  methods: {
    nextStep(value: number) {
      value++;
    },
  },
};
</script>

<template>
  <div>
    <v-container style="border: 1px solid #e0e0e0" class="rounded">
      <v-chip size="x-large" variant="text" style="font-weight: bold">
        <v-icon
          icon="mdi-file-chart-outline"
          color="blue-lighten-1"
          class="mr-1"
        ></v-icon>
        Создание нового отчета
      </v-chip>

      <v-stepper title="sdsdsd" hide-actions v-model="e1" editable>
        <template v-slot:default="{ prev, next }">
          <v-stepper-header>
            <v-stepper-item
              edit-icon=""
              title="Шаблон"
              value="1"
            ></v-stepper-item>
            <v-divider></v-divider>

            <v-stepper-item
              edit-icon=""
              title="Группировки"
              value="2"
            ></v-stepper-item>
            <v-divider></v-divider>

            <v-stepper-item
              edit-icon=""
              title="Показатели"
              value="3"
            ></v-stepper-item>
            <v-divider></v-divider>

            <v-stepper-item
              edit-icon=""
              title="Название и доступ"
              value="4"
            ></v-stepper-item>
          </v-stepper-header>

          <v-stepper-window>
            <v-stepper-window-item value="2">
              <v-card title=" One" flat>...</v-card>
              <v-btn
                style="border: 1px solid #bdbdbd"
                class="mr-3 text-none"
                color="blue-lighten-1"
                variant="outlined"
                @click="next"
                >Продолжить</v-btn
              >
              <v-btn
                style="border: 1px solid #bdbdbd"
                class="text-none"
                color="blue-lighten-1"
                variant="outlined"
                >Отменить</v-btn
              >
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
        </template>
      </v-stepper>
    </v-container>
  </div>
</template>
