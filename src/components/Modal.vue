<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <slot></slot>
      <slot name="links"> </slot>
      <button @click="toggleModal">hide Modal🙈</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "content", "toggleModal"],
  setup() {
    return {}
  },
  methods: {
    closeModal() {
      this.$emit("close")
    }
  }
}
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

.modal h3 {
  color: #03cfba;
  padding-bottom: 10px;
  border-bottom: 1px solid #ddd;
  margin-bottom: 20px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

a {
  color: #03cfba;
  margin-right: 20px;
  display: inline-block;
  font-size: 0.7em;
}
</style>
