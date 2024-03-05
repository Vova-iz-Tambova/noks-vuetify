<template>
  <v-app>
    <v-main>
      <v-theme-provider class="h-100 pa-10" theme="dark" with-background>
        <Report />
      </v-theme-provider>
    </v-main>
  </v-app>
</template>

<script setup lang="ts">
import Report from '@/entities/report-info/ui/add-report-info.vue'
</script>
