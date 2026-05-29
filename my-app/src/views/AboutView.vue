<script setup lang="ts">
import { useTheme } from 'vuetify'

const theme = useTheme()

function toggleTheme() {
  theme.global.name.value = theme.global.current.value.dark ? 'light' : 'dark'
}
</script>

<template>
  <v-main>
    <v-container class="fill-height" fluid>
      <v-row justify="center" align="center" class="fill-height">
        <v-col cols="12" style="max-width: 480px">
          <v-card rounded="xl" elevation="8" class="pa-6 pa-md-8 text-center">

            <div class="d-flex justify-end mb-n2">
              <v-btn
                :icon="theme.global.current.value.dark ? 'mdi-weather-sunny' : 'mdi-weather-night'"
                variant="text"
                @click="toggleTheme"
                :aria-label="theme.global.current.value.dark ? 'Switch to light mode' : 'Switch to dark mode'"
              />
            </div>

            <h1 class="text-h5 font-weight-bold mb-6">About Me</h1>

            <p class="text-body-1 text-medium-emphasis mb-4">
              Hi, I'm Adi Fine — a developer, creator, and builder with a passion for
              crafting clean, purposeful digital experiences.
            </p>
            <p class="text-body-1 text-medium-emphasis mb-6">
              I love working across the stack, from designing interfaces to shipping
              full-featured web apps.
            </p>

            <v-btn variant="text" size="small" to="/" class="text-medium-emphasis">
              ← Back
            </v-btn>

          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
