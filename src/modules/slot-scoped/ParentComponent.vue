<template>
  <div>
    <p>This is a parent component.</p>
    <ChildComponent @on-success="onLoginSuccess" @on-failure="onLoginFailure">
      <template v-slot="{ text }">
        <p>{{ text }}</p>
      </template>
      <template v-slot:namedSlot="{ text, login, loginLoading }">
        <p>{{ text }}</p>
        <button type="button" @click="login" :disabled="loginLoading">
          {{ loginLoading ? "Loading" : "Login" }}
        </button>
      </template>
    </ChildComponent>
  </div>
</template>

<script>
import ChildComponent from "@/modules/slot-scoped/ChildComponent";

export default {
  name: "ParentComponent",
  components: { ChildComponent },
  methods: {
    onLoginSuccess() {
      window.alert("login succeeded");
    },
    onLoginFailure() {
      window.alert("login failed");
    },
  },
};
</script>

<style scoped></style>
