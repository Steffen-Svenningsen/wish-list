<template>
    <div class="modal-bg">
        <div class="modal">
            <div class="image">
                <slot name="image"></slot>
            </div>
            <div class="text">
                <slot name="heading"></slot>
                <slot name="facts"></slot>
                <slot name="links"></slot>
            </div>
            <div class="close-btn">
                <slot name="close-btn"></slot>
            </div>
        </div>
    </div>
</template>


<style lang="sass" scoped>
@import @/assets/main.sass

.modal-bg
  position: fixed
  top: 0
  left: 0
  width: 100vw
  height: 100vh
  background-color: rgba(0, 0, 0, 0.80)
  display: flex
  justify-content: center
  align-items: center

  .modal
    position: relative
    background: $heading
    width: 85%
    height: 85%
    border-radius: 5px
    display: flex
    flex-wrap: wrap
    box-shadow: 6px 6px 8px rgba(255, 255, 255, 0.20)

    div

        &:nth-of-type(1),
        &:nth-of-type(2)
            min-width: 200px
            padding: 2rem
            flex: 40%

    .image

    .text

    .close-btn
        position: absolute
        top: 15px
        right: 15px
        
</style>