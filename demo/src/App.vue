<template>
  <div class='demo_container'>
    <file-read-comp
        read_label="Read File Path"
        :read_file="read_file"
        :css_variables="css_variables"
        v-on:file_read_comp_filename_changed="filename_changed"
        v-on:file_read_comp_content_changed="content_changed">
    </file-read-comp>
    <p>(See console for output)</p>
  </div>
</template>

<script>
  import FileReadComp from 'filereadcomp';

  export default {
    name: 'App',
    data: function() {
      return {
        read_file: true,
        css_variables: {
          file_read_comp_heading_color: 'white',
          file_read_comp_label_color: 'white',
          file_read_comp_label_border_color: 'white',
          file_read_comp_label_focus_background: 'gold'
        }
      };
    },
    components: {
      FileReadComp
    },
    methods: {
      filename_changed: function(filename){
        console.log(`FileName: ${filename}`);
      },
      content_changed: function(content){
        console.log(`File Content: ${content}`);
      }
    }
  }
</script>

<style>
  .demo_container {
    width: 100%;
    height: 100%;
    min-height: 40rem;
    max-width: 60rem;
    color: white;
    background-color: black;
    padding: 2rem;
  }
  p {
    margin-top: 1rem;
  }
</style>