<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="generateReport()">generate</button>
    <vue3-html2pdf
      :show-layout="false"
      :float-layout="true"
      :enable-download="true"
      :preview-modal="true"
      :paginate-elements-by-height="1400"
      filename="hee hee"
      :pdf-quality="2"
      :manual-pagination="false"
      pdf-format="a4"
      pdf-orientation="landscape"
      pdf-content-width="800px"
      ref="html2Pdf"
    >
      <!--      @progress="onProgress($event)"-->
      <!--      @hasStartedGeneration="hasStartedGeneration()"-->
      <!--      @hasGenerated="hasGenerated($event)"-->
      <template v-slot:pdf-content>
        <section>
          <!-- PDF Content Here -->
          <h1>dupa jasia</h1>
        </section>
      </template>
    </vue3-html2pdf>
  </div>
</template>

<script lang="ts">
import Vue3Html2pdf from "vue3-html2pdf";

export default {
  components: {
    Vue3Html2pdf,
  },
  methods: {
    generateReport() {
      console.log("=>(AboutView.vue:36) generateReport");
      this.$refs.html2Pdf.generatePdf();
    },
  },
};
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
