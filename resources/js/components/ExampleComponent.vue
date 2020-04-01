<template>
  <div style="height: 100vh;
        width: 220vh;
        position: fixed;
        top: 0;
        z-index: 1;">
    <vue-draggable-resizable :w="400" :h="150"  @dragging="onDrag" @resizing="onResize" :parent="true">
        <iframe width="100%" height="auto"
            src="https://www.youtube.com/embed/tgbNymZ7vqY">
        </iframe>
    </vue-draggable-resizable>
  </div>
</template>

<script>
import VueDraggableResizable from 'vue-draggable-resizable'

export default {
  data: function () {
    return {
      width: 0,
      height: 0,
      x: 100,
      y: 0
    }
  },
  methods: {
    onResize: function (x, y, width, height) {
      this.x = x
      this.y = y
      this.width = width
      this.height = height
    },
    onDrag: function (x, y) {
      this.x = x
      this.y = y
    }
  }
}
</script>
