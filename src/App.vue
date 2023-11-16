<script>
  import Banner from './components/Banner.vue';
import BodyComponent from './components/BodyComponent.vue';

  export default {
    components:{
    Banner,
    BodyComponent
}
  }

</script>

<template>
  <Banner/>
  <BodyComponent/>
</template>

<style scoped>
.banner {
  padding: 4rem 7.5rem;
  color: var(--creme);

  display: flex;
  justify-content: space-between;
  align-items: center;
  column-gap: 3.25rem;
}

.logo {
  height: 4.5rem;
  margin-bottom: 3rem;
}

.header-phrase{
  margin-bottom: 2rem;
}

.green-text {
  color: var(--verde-medio, #3D6D4A);
}

.banner-photo{
  width: 35rem;
}

@media only screen and (max-width: 1300px) {
  .banner {
    padding: 4rem 3.75rem;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  .logo {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
}

@media only screen and (max-width: 767px) {
  .banner {
    padding: 4rem 1.5rem;
  }

  .banner-photo {
    width: min(100%, 21.25rem);
  }
}
</style>