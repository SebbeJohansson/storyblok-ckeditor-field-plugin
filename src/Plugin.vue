<template>
  <div>
    <ckeditor :editor="editor" v-model="model.content" :config="editorConfig"></ckeditor>
  </div>
</template>

<script>
import ClassicEditor from '@ckeditor/ckeditor5-build-classic';
export default {
  mixins: [window.Storyblok.plugin],
  data() {
    return {
      editor: ClassicEditor,
      editorConfig: {
        // The configuration of the editor. https://ckeditor.com/docs/ckeditor5/latest/installation/frameworks/vuejs-v2.html#config
      }
    };
  },
  methods: {
    initWith() {
      return {
        plugin: 'ckeditor',
        content: '',
      };
    },
  },
  watch: {
    'model': {
      handler: function (value) {
        this.$emit('changed-model', value);
      },
      deep: true
    }
  }
};
</script>