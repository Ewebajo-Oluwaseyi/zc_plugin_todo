<template>
    <div class="modal shadow-md">
        <div class="grid overflow-visible text-sm rounded-md shadow-md modal-items w-44 grid-row-5">
            <div class="flex flex-col mt-8 mb-0 items">
                <span class="rounded-sm py-2 px-4 cursor-pointer" v-for="(link, index) in deleteLinks" :key="index" @clink="link.action">
                    {{link.name}}
                </span>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    name: 'modal',
      props: {
          deleteLinks:  {
            type: Array
          }
      }
  }
</script>

<style lang="scss" scoped>

</style>