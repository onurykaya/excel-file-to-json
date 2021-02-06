<template>
  <div class="container">
    <h3>Excel Dosyasını Ekleyin</h3>
    <input type="file" class="custom-file-input" @change="onChange" />
    <c-link href="https://jsonformatter.curiousconcept.com/#" is-external>
      Json formatını düzeltmek için Json Formattera gidin...
    </c-link>
    <xlsx-read :file="data">
      <xlsx-json>
        <template #default="{collection}">
          <div class="words">
            {{ collection }}
          </div>
        </template>
      </xlsx-json>
    </xlsx-read>
  </div>
</template>

<script>
import XlsxRead from "../../node_modules/vue-xlsx/dist/components/XlsxRead";
import XlsxJson from "../../node_modules/vue-xlsx/dist/components/XlsxJson";
import { CLink } from "@chakra-ui/vue";

export default {
  components: {
    XlsxRead,
    XlsxJson,
    CLink
  },
  data() {
    return {
      data: null
    };
  },
  methods: {
    onChange(event) {
      this.data = event.target.files ? event.target.files[0] : null;
    }
  }
};
</script>

<style scoped>
.words {
}
.container {
  color: black;
}
*,
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  color: white;
}

body {
  margin: 0;
  padding: 2rem 1.5rem;
  font: 1rem/1.5 "PT Sans", Arial, sans-serif;
  color: #ffffff;
}
.custom-file-input::-webkit-file-upload-button {
  visibility: hidden;
}
.custom-file-input {
  margin-top: 20px;
  margin-bottom: 20px;
  width: 100%;
}
.custom-file-input::before {
  content: "Json formatına dönüştürmek için bir dosya seçin...";
  display: inline-block;
  background: linear-gradient(top, #f9f9f9, #e3e3e3) !important;
  border: 1px solid #999;
  border-radius: 3px;
  padding: 5px 8px;
  outline: none;
  white-space: nowrap;
  -webkit-user-select: none;
  cursor: pointer;
  text-shadow: 1px 1px #fff;
  font-weight: 700;
  font-size: 10pt;
}
.custom-file-input:hover::before {
  border-color: black;
}
.custom-file-input:active::before {
  background: -webkit-linear-gradient(top, #e3e3e3, #f9f9f9);
}
.words {
  margin-bottom: 20px;
  margin-top: 20px;
}
</style>
