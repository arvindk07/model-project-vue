<template>
  <div class="backdrop">
    <div class="modal">
      <h1>Modal Title</h1>
      <p>Modal Content</p>
    </div>
  </div>
</template>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  border-radius: 10px;
  background: #fff;
}
.backdrop {
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
}
.modal h1 {
  color: #03cfb4;
  border-bottom: none;
  padding: 0;
}

.modal p {
  font-style: normal;
}
</style>
