<template>
  <div>
    <Prism class="mt-3" code="<Button>Default button</Button>">
      <Button>Default button</Button>
    </Prism>

    <Prism class="mt-3" code="<Button color='primary'>Primary button</Button>">
      <Button color="primary">Primary button</Button>
    </Prism>

    <Prism
      class="mt-3"
      code="<Button color='secondary'>Secondary button</Button>"
    >
      <Button color="secondary">Secondary button</Button>
    </Prism>

    <Prism class="mt-3" code="<Button color='success'>Success button</Button>">
      <Button color="success">Success button</Button>
    </Prism>

    <Prism class="mt-3" code="<Button color='danger'>Danger button</Button>">
      <Button color="danger">Danger button</Button>
    </Prism>

    <Prism class="mt-3" code="<Button color='warning'>Warning button</Button>">
      <Button color="warning">Warning button</Button>
    </Prism>

    <Prism
      class="mt-3"
      code="<Button color='primary' :loading='true'>Primary button</Button>"
    >
      <Button color="primary" :loading="true"> Primary button </Button>
    </Prism>

    <Prism
      class="mt-3"
      code="<Button color='#1ca1e3' fontColor='#ffffff'>Custom button</Button>"
    >
      <Button color="#1ca1e3" fontColor="#ffffff"> Custom button </Button>
    </Prism>
  </div>
</template>

<script>
export default {};
</script>
