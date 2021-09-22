<template>
    <div class="overlay">
        <form class="w-4/5 p-4 bg-white rounded">
         <button class="flex mb-2 border content-right mx-right justify-items-end position-absolute btn-close"
            type="button" @click="close">
            x
         </button>
            <div>Delete Modal</div>
        </form>
    </div>
</template>

<script>
    export default {
      name: 'Delete Modal',
      methods: {
        close() {
          this.$emit('toggleMenu');
        }
     }
    }
</script>

<style lang="scss" scoped>
     .overlay {
     width: 100%;
     display: flex;
     justify-content: center;
     align-items: center;
     position: fixed;
     top: 0;
     bottom: 0;
     left: 0;
     z-index: 2;
      background: rgba(0, 0, 0, 0.14901960784313725);
   }
    .btn-close {
    position: absolute;
    top: 20px;
    right: 0;
    z-index: 100;
    overflow: auto;
    overflow-y: auto;
    background-color: white;
  }

</style>