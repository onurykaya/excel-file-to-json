<template>
  <div class="container">
    <c-box
      v-for="pharmacy in pharmacyList"
      v-bind:key="pharmacy.loc"
      maxW="sm"
      border-width="1px"
      rounded="lg"
      overflow="scroll"
      mt="3"
      mb="3"
      mr="5"
      height="350px"
      background-color="white"
    >
      <c-image
        src="http://www.arti392.com/images/haberler/2019/04/nobetci_eczaneler_h23679_e66ca.jpg"
        :alt="property.imageAlt"
        max-height="200px"
        width="100%"
      />
      <c-box p="6">
        <c-box
          mt="1"
          font-weight="semibold"
          as="h4"
          line-height="tight"
          is-truncated
          text-align="center"
          mb="4"
        >
          {{ pharmacy.name }} ECZANESİ
        </c-box>
        <c-box
          mt="1"
          font-weight="semibold"
          as="h4"
          line-height="tight"
          is-truncated
          text-align="center"
        >
          Adres: {{ pharmacy.address }}
        </c-box>
        <c-box
          mt="4"
          text-align="center"
          font-weight="bold"
          as="h1"
          line-height="tight"
        >
          Telefon: <a href="tel:'`${pharmacy.phone}`">{{ pharmacy.phone }}</a>
        </c-box>
      </c-box>
    </c-box>
  </div>
</template>

<script>
export default {
  name: "Example",
  props: ["pharmacyList"],
  data() {
    return {
      imageUrl: [
        "https://lh3.googleusercontent.com/proxy/Ap77FYHu3sZ5_cgUvvh8lgSEds0Ebqx7x8V5JUyEKIgJihLGx8r2V1Sw-1rtSRKD333g1ruUP4Wp835d7sbXyRg2uQ_DraXFLrry_Sz0xvGt4vynJGr-Lao",
        "https://www.artdehuile.com/gorseller/komponent/buyuk-slider/komponent3937.jpg"
      ],
      property: {
        imageAlt: "Rear view of modern home with pool",
        beds: 3,
        baths: 2,
        title:
          "Modern home in city center in the heart of historic Los Angeles",
        formattedPrice: "$1,900.00",
        reviewCount: 34,
        rating: 4
      }
    };
  }
};
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 100px;
}
</style>
