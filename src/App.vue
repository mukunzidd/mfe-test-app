<template>
  <FrameworkWrapper :config="config">
    <template #header>
      <header class="header">
        <h1>Vue MFE Project</h1>
      </header>
    </template>

    <div class="content">
      <!-- Your content here -->
       <TodoList theme="dark" />
       <Counter :initial-count="0" theme="light" />
    </div>

    <template #footer>
      <footer class="footer">
        <p>&copy; 2024 Vue MFE Project</p>
      </footer>
    </template>
  </FrameworkWrapper>
</template>

<script setup lang="ts">
import { FrameworkWrapper } from '@mknz/vue-mfe-wrapper'
import type { FrameworkConfig } from '@mknz/vue-mfe-wrapper'
import {TodoList, VueMfeFeatureB} from './features'
import '@mknz/vue-mfe-feature-b/style.css'
import { VueMfeFeatureA,Counter } from '@mknz/vue-mfe-feature-a'
import '@mknz/vue-mfe-feature-a/style.css'

const config: FrameworkConfig = {
  features: [VueMfeFeatureB, VueMfeFeatureA]
}
</script>

<style scoped>
.header {
  padding: 1rem;
  background-color: #42b883;
  color: white;
}

.content {
  padding: 1rem;
}

.footer {
  padding: 1rem;
  background-color: #35495e;
  color: white;
  text-align: center;
}
</style>