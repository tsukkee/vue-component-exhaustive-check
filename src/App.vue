<script setup lang="ts">
import ExhaustiveCheck from './components/ExhaustiveCheck.vue'

type CardAType = {
  type: 'A'
  id: number
  name: string
}
type CardBType = {
  type: 'B'
  id: number
  label: string
}
type CardCType = {
  type: 'C'
  id: number
  title: string
}
type Card = CardAType | CardBType | CardCType

const cards: Card[] = [
  {
    type: 'A',
    id: 0,
    name: 'Card A'
  },
  {
    type: 'B',
    id: 1,
    label: 'Card B'
  },
  {
    type: 'C',
    id: 2,
    title: 'Card C'
  }
]
</script>

<template>
  <div v-for="card in cards" :key="card.id">
    <div v-if="card.type === 'A'">
      {{ card.name }}
    </div>
    <div v-else-if="card.type === 'B'">
      {{ card.label }}
    </div>
    <div v-else-if="card.type === 'C'">
      {{ card.title }}
    </div>
    <div v-else>
      <ExhaustiveCheck :check="card" />
    </div>
  </div>
</template>
