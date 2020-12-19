<template>
  <div>
    <Prism class="mt-3" :code="prismCode">
      <Alert :show="show" @close="show = false" />
      <div @click="show = !show">open modal</div>
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
      prismCode: `<Modal :show="show" @close="show = false" />
<div @click="show = !show">open modal</div>`,
    };
  },
};
</script>
