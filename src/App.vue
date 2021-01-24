<template>
  <c-theme-provider>
    <c-reset />
    <!--Your application goes here -->
    <Container>
      <router-view />
    </Container>
  </c-theme-provider>
</template>

<script>
import { CThemeProvider, CReset } from "@chakra-ui/vue";
import Container from "@/components/Container";
export default {
  name: "App",
  components: {
    Container,
    CThemeProvider,
    CReset
  }
};
</script>
