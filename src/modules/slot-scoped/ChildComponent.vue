<template>
  <div>
    <p>This is a child component</p>
    <div>
      <p>Default Slot</p>
      <slot :text="defaultSlotText"></slot>
    </div>

    <div>
      <p>Named Slot</p>
      <slot
        name="namedSlot"
        :text="namedSlotText"
        :login="login"
        :loginLoading="loginLoading"
      ></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      defaultSlotText: "Default Slot text",
      namedSlotText: "Named Slot text",
      loginLoading: false,
    };
  },
  methods: {
    login() {
      console.log("login start");
      this.loginLoading = true;
      setTimeout(() => {
        this.loginLoading = false;
        const random = Math.floor(Math.random() * 10);
        if (random % 2) {
          this.onSuccess();
        } else {
          this.onFailure();
        }
      }, 1000);
    },
    onSuccess() {
      this.$emit("on-success");
    },
    onFailure() {
      this.$emit("on-failure");
    },
  },
};
</script>

<style scoped></style>
