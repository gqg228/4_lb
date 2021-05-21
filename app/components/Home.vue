<template>
    <Page class="v" >
      <ActionBar title="CallCull" class="act"/>
        <CallCull></CallCull>  
    </Page>
</template>

<script>
  import TodoItem from './CallCull.vue';
    export default{
      components :{ TodoItem }
    }
</script>

<style>
  .act{
    background-color: #cc9b6d;
  }
</style>