<script >
import Tag from './Tag.vue';

export default {
    setup() {
        return {};
    },
    components: { Tag },
    props: {
        texto: {type: String, required: true}
    },
    data(){
        return{
            selected: false,
        }
    },
    methods:{
       onAdd(){
        this.selected = !this.selected

        if(this.selected){
            this.$emit('selectedIngredient', this.ingredient)
        }
       } 
    },

    emits: ['selectedIngredient']
}
</script>

<template>
    <button 
        @click="onAdd"
       :aria-pressed="selected"
        class="card"
    >
        <Tag :texto="texto" :active="selected" />
    </button>
</template>

<style lang="css" scoped>
    .card{
        cursor: pointer;
    }
</style>