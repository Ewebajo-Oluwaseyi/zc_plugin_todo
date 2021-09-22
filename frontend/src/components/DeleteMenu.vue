<template>
    <div class="modal shadow-md">
        <div class="grid overflow-visible bg-white text-sm rounded-md shadow-md modal-items w-30 grid-row-5">
            <div class="flex flex-col mb-0 items">
                <span class="rounded-sm py-3 px-4 text-dark font-bold cursor-pointer border-b border-green-400" v-for="(link, index) in deleteLinks" :key="index" @click="link.action">
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

<style scoped>
.modal-items {
    position: absolute;
    top: 90px;
    right:5px;
    z-index: 100;
    overflow: auto;
    overflow-y: auto;
    /* background-color: white; */
  }
</style>