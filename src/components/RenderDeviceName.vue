<script setup>
import { useI18n } from 'vue-i18n';

const { t: $t } = useI18n();
const props = defineProps({
  device: Object,
});
</script>

<template>
  <span>{{
    device['nickName'] && device['nickName'].length > 0
      ? device['nickName']
      : device['chiName'] && device['chiName'].length > 0
      ? device['chiName']
      : device['name'] && device['name'].length > 0
      ? device['name']
      : $t('form.unknown')
  }}</span>
</template>
