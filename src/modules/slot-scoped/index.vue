<template>
  <ParentComponent></ParentComponent>
</template>

<script>
import ParentComponent from "@/modules/slot-scoped/ParentComponent";

export default {
  name: "SlotScopedDemo",
  components: { ParentComponent },
};
</script>

<style scoped></style>
