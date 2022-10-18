<template>
  <div id="drag" class="mx-auto text-center row">
    <div id="dragHandle" class="text-center mb-2">
      <span class="lead fw-bold">Drag Here</span>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "VueDragger",
  props: {
    onDragStart: Function,
    onDragEnd: Function,
  },
  methods: {
    initDrag(e) {
      let draggableDiv = document.getElementById("drag");
      let style = window.getComputedStyle(draggableDiv);
      let left = parseInt(style.left);
      let top = parseInt(style.top);

      draggableDiv.style.left = e.movementX + left + "px";
      draggableDiv.style.top = e.movementY + top + "px";
    },
  },

  mounted() {
    let dragHandleDiv = document.getElementById("dragHandle");
    dragHandleDiv.addEventListener("mousedown", () => {
      this.onDragStart();
      dragHandleDiv.classList.add("active");
      dragHandleDiv.addEventListener("mousemove", this.initDrag);
    });
    document.addEventListener("mouseup", () => {
      this.onDragEnd();
      dragHandleDiv.classList.remove("active");
      dragHandleDiv.removeEventListener("mousemove", this.initDrag);
    });
  },
};
</script>

<style scoped>
#drag {
  position: absolute;
  border-radius: 4px;
}

#dragHandle {
  cursor: move;
  height: 20px;
}
</style>
