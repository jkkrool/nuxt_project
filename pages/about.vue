<template>
  <div class="about-us">
    <div class="container">
      <section class="company-info">
        <h2>Witaj! </h2>
        <button @click="toggleText" class="button">Poznaj nas</button>
        <p v-if="showText">
          
Jesteśmy firmą z ponad dekadą doświadczenia, 
aktywnie rozwijającą swoją działalność. 
Naszym priorytetem jest dostarczanie klientom 
produktów najwyższej jakości z całego globu, przy 
jednoczesnym zachowaniu przystępnych cen. Nasza 
oferta obejmuje szeroki wachlarz kategorii, od 
nowoczesnej elektroniki, przez modę, po 
różnorodne artykuły do użytku domowego.

        </p>
      </section>
      <section class="team">
        <h2>Nasz zespół</h2>
        <div class="team-member">
          <img src="http://localhost:3000/personel1.jpg" alt="Zdjęcie pracownika" />
          <h3>Kamil Niedźwiedź</h3>
          <p>Dyrektor generalny</p>
        </div>
        <div class="team-member">
          <img src="http://localhost:3000/personel2.jpg" alt="Zdjęcie pracownika" />
          <h3>Roman Pollski</h3>
          <p>Specjalistka ds. kontaktów z klientem</p>
        </div>
        <div class="team-member">
          <img src="http://localhost:3000/personel3.jpg" alt="Zdjęcie pracownika" />
          <h3>Zofia Niepołomicka</h3>
          <p>Specjalista relacji międzyludzkich</p>
        </div>
        <div class="team-member">
          <img src="http://localhost:3000/personel4.jpg" alt="Zdjęcie pracownika" />
          <h3>Jerzy Clooney</h3>
          <p>Specjalista ds. IT</p>
        </div>
      </section>
    
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const showText = ref(false);

    const toggleText = () => {
      showText.value = !showText.value;
    };

    return { showText, toggleText };
  },
};
</script>

<style scoped>
.about-us {
  padding: 50px 0;
}

.container {
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
}

.company-info,
.team {
  margin-bottom: 40px;
}

h2 {
  margin-bottom: 20px;
}

.team-member {
  margin-top: 30px;
}

.team-member img {
  width: 150px;
  border-radius: 50%;
}

.team-member h3 {
  margin-top: 10px;
}

.team-member p {
  font-style: italic;
}
</style>
