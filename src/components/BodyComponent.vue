<script>
import SelectIngredients from './SelectIngredients.vue';
import Tag from './Tag.vue';
export default {
  data() {
    return {
      ingredients: []
    }
  },
  components: {
    SelectIngredients,
    Tag
  },
  methods: {
    onAdd(ingredient2) {
      this.ingredients.push(ingredient2)
      console.log(ingredient2)
    }
  },
}
</script>

<template>
  <main class="principal-content">
    <section>
      <span class="subtitle-lg your-list-text">
        Sua lista:
      </span>

      <ul v-if="ingredients.length" class="your-list-ingredients">
        <li v-for="ingredient in ingredients" :key="ingredient" class="ingredients">
          <Tag :texto="ingredient" active  />
        </li>
      </ul>

      <p v-else class="paragraph empty-list">
        <img src="../images/icones/lista-vazia.svg" alt="">
        Sua lista está vazia, selecione ingredientes para iniciar.
      </p>
    </section>
    <SelectIngredients @selectedIngredient='onAdd'/>
  </main>
</template>

<style scoped>
.principal-content {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #FFFAF3);
  color: var(--cinza, #444);

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}

.your-list-text {
  color: var(--coral, #F0633C);
  display: block;
  text-align: center;
  margin-bottom: 1.5rem;
}

.your-list-ingredients {
  display: flex;
  justify-content: center;
  gap: 1rem 1.5rem;
  flex-wrap: wrap;
}


.empty-list {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.25rem;

  color: var(--coral, #F0633C);
  text-align: center;
}

@media only screen and (max-width: 1300px) {
  .principal-content {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .principal-content {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}
</style>