<template>
  <div>
    <Prism class="mt-3 custom-prism" title="Prism Card" :code="prismCode">
      <Prism title="button" code="<Button>Default button</Button>">
        <Button>Default button</Button>
      </Prism>
    </Prism>
  </div>
</template>

<script>
export default {
  data() {
    return {
      prismCode: `<Prism title="button" code="<Button>Default button</Button>">
  <Button>Default button</Button>
</Prism>`,
    };
  },
};
</script>

<style>
.custom-prism {
  background: rgb(255, 246, 217) !important;
}
</style>
