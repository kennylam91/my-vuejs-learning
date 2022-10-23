<template>
  <div>
    <p>This is a child component</p>
    <div>
      <p>Default Slot</p>
      <slot :text="defaultSlotText"></slot>
    </div>

    <div>
      <p>Named Slot</p>
      <slot name="namedSlot" :text="namedSlotText"></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      defaultSlotText: "Default Slot text",
      namedSlotText: "Named Slot text"
    };
  }
};
</script>

<style scoped></style>
