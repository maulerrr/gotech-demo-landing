<script setup lang="ts">
import { locale } from '@/composables/useLocale';
import {
  Select,
  SelectTrigger,
  SelectValue,
  SelectContent,
  SelectItem,
} from '@/components/ui/select';
</script>

<template>
  <Select v-model="locale">
    <SelectTrigger size="sm" variant="ghost" class="w-24">
      <SelectValue placeholder="Lang" />
    </SelectTrigger>
    <SelectContent>
      <SelectItem value="en">English</SelectItem>
      <SelectItem value="ru">Русский</SelectItem>
      <SelectItem value="kk">Қазақша</SelectItem>
    </SelectContent>
  </Select>
</template>
