<template>
  <q-item
    clickable
    tag="a"
    :href="props.meta.link"
  >
    <q-item-section
      v-if="props.meta.icon"
      avatar
    >
      <q-avatar>
        <img :src="props.meta.icon">
      </q-avatar>
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ props.meta.title }}</q-item-label>
      <q-item-label caption>{{ props.meta.caption }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script setup>

defineOptions({
  name: 'EssentialLink'
})

const props = defineProps({
  name: {
    type: String,
    default: '포슬립 계산기 허브'
  },

  meta: {
    title: {
      type: String,
      required: true
    },
    caption: {
      type: String,
      default: ''
    },
    icon: {
      type: String,
      default: ''
    },
    link: {
      type: String,
      default: '#'
    }
  }
})
</script>
