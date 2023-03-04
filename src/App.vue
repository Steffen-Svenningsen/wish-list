<script setup lang="ts">
import Modal from "@/components/VueModal.vue";
import { ref } from 'vue';

const BackboneOpen = ref(false);
const BarbermaskineOpen = ref(false);
const TshirtOpen = ref(false);
const AsicsOpen = ref(false);
const HairDryerOpen = ref(false);
const TennisOpen = ref(false);
const SamsungOpen = ref(false);
const modal = ref(null);
</script>

<template>
  <main>
    <h1>Steffens ønskeliste</h1>
    <div class="line"></div>
    <p>Her kan du se alle Steffens ønsker anno 2023. Tryk på ønskerne for at se mere om produktet og hvor du evt. kan købe det.</p>
    <div class="container">
      <div @click="BackboneOpen = true" class="wish">Open</div>
      <div @click="BarbermaskineOpen = true" class="wish">Open</div>
      <div @click="TshirtOpen = true" class="wish">Open</div>
      <div @click="AsicsOpen = true" class="wish">Open</div>
      <div @click="HairDryerOpen = true" class="wish">Open</div>
      <div @click="TennisOpen = true" class="wish">Open</div>
      <div @click="SamsungOpen = true" class="wish">Open</div>
    </div>
    <Teleport to="#modal">
      <Modal v-if="BackboneOpen">Backbone</Modal>
    </Teleport>
    <Teleport to="#modal">
      <Modal ref="modal" class="modal" v-if="BarbermaskineOpen">
        <template v-slot:image>
          <img width="200" height="200" src="../public/barbermaskine.webp" alt="Xiaomi Barbermaskine">
        </template>
        <template v-slot:heading>
          Xiaomi Barbermaskine
        </template>
        <template v-slot:facts>
          <p><span class="bold">Mærke:</span> Xiaomi</p> <br> <p><span class="bold">Mærke:</span> Xiaomi</p>
        </template>
        <template v-slot:links>
          <a href="#">Link</a>
        </template>
        <template v-slot:close-btn>
          <button class="close-btn" @click="BarbermaskineOpen = false">Luk</button>
        </template>
      </Modal>
    </Teleport>
    <Teleport to="#modal">
      <Modal v-if="TshirtOpen">Hvide Tshirts</Modal>
    </Teleport>
    <Teleport to="#modal">
      <Modal v-if="AsicsOpen">Løbesko</Modal>
    </Teleport>
    <Teleport to="#modal">
      <Modal v-if="HairDryerOpen">Hårtørrer</Modal>
    </Teleport>
    <Teleport to="#modal">
      <Modal v-if="TennisOpen">Tennisketcher</Modal>
    </Teleport>
    <Teleport to="#modal">
      <Modal v-if="SamsungOpen">Oplader til Samsung Watch</Modal>
    </Teleport>
  </main>
</template>

<style lang="sass" scoped>
@import @/assets/main.sass

main
  width: 100%
  height: 100%
  padding: 2rem

  .line
    width: clamp(60px, 10vw, 120px)
    height: 2px
    background-color: $cta
    margin-top: 6px

  .container
    display: flex
    flex-wrap: wrap
    margin-top: 4rem
    width: 100%
    height: 100%
    justify-content: space-between
    gap: 2rem

    .wish
      background: white
      padding: 2rem
      border-radius: 5px
      min-width: 200px

.modal
    img
      border-radius: 5px
      width: 100%
      height: auto

</style>
