<template>
  <div>
    <p>This is a parent component.</p>
    <ChildComponent>
      <template v-slot="{text}">
        <p>{{ text }}</p>
      </template>
      <template v-slot:namedSlot="{text}">
        <p>{{ text }}</p>
      </template>
    </ChildComponent>
  </div>
</template>

<script>
import ChildComponent from "@/modules/slot-scoped/ChildComponent";

export default {
  name: "ParentComponent",
  components: { ChildComponent }
};
</script>

<style scoped>

</style>