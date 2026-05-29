<script setup lang="ts">
import { useTheme } from 'vuetify'
import LinkButton from '@/components/LinkButton.vue'

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

            <v-avatar size="96" color="surface-variant" class="mb-4" />

            <h1 class="text-h5 font-weight-bold mb-1">Adi Fine</h1>
            <p class="text-body-2 text-medium-emphasis mb-6">Developer · Creator · Builder</p>

            <div class="d-flex flex-column ga-3 mb-4">
              <LinkButton label="Portfolio" url="#" icon="mdi-briefcase-outline" />
              <LinkButton label="LinkedIn" url="https://linkedin.com/in/adifine" icon="mdi-linkedin" />
              <LinkButton label="Email" url="mailto:adi@example.com" icon="mdi-email-outline" />
            </div>

            <v-btn variant="text" size="small" to="/about" class="text-medium-emphasis">
              About me →
            </v-btn>

          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>
