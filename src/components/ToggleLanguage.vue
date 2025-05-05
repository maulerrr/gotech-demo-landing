<script setup lang="ts">
import { locale } from '@/composables/useLocale';
import {
  Select,
  SelectTrigger,
  SelectValue,
  SelectContent,
  SelectItem,
} from '@/components/ui/select';
import { Languages } from 'lucide-vue-next'; // Import the Languages icon
</script>

<template>
  <Select v-model="locale">
    <SelectTrigger size="sm" variant="ghost" class="">
      <!-- Use the Languages icon as the placeholder -->
      <SelectValue>
        <Languages class="h-4 w-4" />
      </SelectValue>
    </SelectTrigger>
    <SelectContent>
      <SelectItem value="en">English</SelectItem>
      <SelectItem value="ru">Русский</SelectItem>
      <SelectItem value="kk">Қазақша</SelectItem>
    </SelectContent>
  </Select>
</template>