<template>
  <div class="mt-4">
    <file-pond
      name="image"
      ref="pond"
      lable-idle="Click to choose image or drag here"
      server="/upload"
      @init="filepondInitialized"
      accepted-file-types="image/*"
    />
  </div>
</template>

<script>
import vueFilePond from "vue-filepond";
import "filepond/dist/filepond.min.css";
import FilePondPluginFileValidateType from "filepond-plugin-file-validate-type";

const FilePond = vueFilePond(FilePondPluginFileValidateType);

export default {
  components: {
    FilePond,
  },

  methods: {
    filepondInitialized() {
      console.log("Filepond ready");
      console.log("Filepond object:", this.$refs.pond);
    },
  },
};
</script>