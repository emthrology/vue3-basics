<template >
  <div class="modals">
    <h1>Modals</h1>
    <button @click="showModal = true">showModal</button>
    <!-- teleport: move the tag to the place where you want to  -->
    <!-- check it out with browser dev tools -->
    <teleport to=".modals-container"> 
      <div class="modal" v-if="showModal">
        <h1>this is a modal</h1>
        <p >Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos ea, tenetur eaque ipsam labore enim placeat amet exercitationem sint magni! Hic consequuntur consequatur obcaecati, tempora, repellendus unde ut ipsum, sint dolor architecto sapiente libero eos a reprehenderit numquam animi natus suscipit. Nemo voluptas obcaecati sunt ullam at quasi vel cum!</p>
        <button @click="showModal = false">HideModal</button>
      </div>
    </teleport>
  </div>
</template>
<script setup>
  import {ref} from 'vue'
  /*
    modals
  */
  const showModal = ref(false)
</script>
<style>
  .modal {
    background: beige;
    padding: 10px;
    color: black;

    position: apsolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index:999;
  }
</style>