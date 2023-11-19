<script lang="ts">
import Tag from './Tag.vue';

export default {
    props: {
        categorie: { type: Object, required: true }
    },
    components: { Tag }
}
</script>

<template>
    <article class="categorie">
        <header class="categorie__header">
            <img :src="`/ingredientes/${categorie.imagem}`" alt="" class="categorie__image">
        </header>

        <h2 class="paragraph-lg categorie__name">{{ categorie.nome }}</h2>

        <ul class="categorie__ingredients">
            <li v-for="ingredient in categorie.ingredientes" :key="ingredient">
                <Tag :texto="ingredient"/>
            </li>
        </ul>
    </article>
</template>


<style scoped>
.categorie {
  width: 19.5rem;
  padding: 1rem;
  border-radius: 1rem;
  background: var(--branco, #FFF);
  box-shadow: 4px 4px 10px 0px rgba(68, 68, 68, 0.05);
  height: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}

.categorie__header {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.categorie__image {
  width: 3.5rem;
}

.categorie__name {
  text-align: center;
  color: var(--verde-medio, #3D6D4A);
  font-weight: 700;
}

.categorie__ingredients {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  flex-wrap: wrap;
}
</style>