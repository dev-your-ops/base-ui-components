<template>
  <div>
    <Prism class="mt-3" :code="prismCode">
      <Modal :show="show" @close="show = false">
        <div class="p-2">
          <div @click="show = false" class="text-xl cursor-pointer">
            close &times;
          </div>
        </div>
      </Modal>

      <div @click="show = true">open modal</div>
    </Prism>
  </div>
</template>

<script>
export default {
  methods: {
    close() {
      console.log('close');
      this.show = false;
    },
  },
  data() {
    return {
      show: false,
      prismCode: `<Modal :show="show" @close="show = false">
  <div class="p-2">
    <div @click="show = false" class="text-xl cursor-pointer">
      close &times;
    </div>
  </div>
</Modal>

<div @click="show = !show">open modal</div>`,
    };
  },
};
</script>
