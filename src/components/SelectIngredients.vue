<script>
import {getCategories} from '../http/getCategories'
import CardIngredients from './CardIngredients.vue';
export default {
    data() {
        return {
            categories: []
        };
    },
    async created() {
        this.categories = await getCategories();
    },
    components: { CardIngredients },
    emits: ['selectedIngredient']
}
</script>

<template>
  <section class="select-ingredients">
    <h1 class="header ingredients-title">Ingredientes</h1>

    <p class="paragraph-lg instructions">
      Selecione abaixo os ingredientes que você quer usar nesta receita:
    </p>

    <ul class="categories">
      <li v-for="categorie in categories">
        <CardIngredients :categorie="categorie"  @selectedIngredient = '$emit("selectedIngredient", $event)' />
      </li>
    </ul>

    <p class="paragraph hint">
      *Atenção: Consideramos que você tem em casa sal, pimenta e água
    </p>

  </section>
</template>

<style scoped>
.select-ingredients {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.ingredients-title {
  color: var(--verde-medio, #3D6D4A);
  display: block;
  margin-bottom: 1.5rem;
}

.instructions {
  margin-bottom: 2rem;
}

.categories {
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.hint {
  align-self: flex-start;
  margin-bottom: 3.5rem;
}

@media only screen and (max-width: 767px) {
  .hint {
    margin-bottom: 2.5rem;
  }
}
</style>
