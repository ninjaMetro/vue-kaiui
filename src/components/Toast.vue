<template>
  <transition name="fade">
    <div class="kaiui-toast" v-if="shouldShow">
      <span class="kaiui-h1 kaiui-toast-text">{{ title }}</span>
    </div>
  </transition>
</template>

<script>
/**
 * **PRIVATE: This component is automatically integrated as a global Mixin. Just use**
 *
 * `this.showToast("I'm a Toast")`
 *
 * **in any of your components.**
 *
 * @author Sebastian Baar
 * @license MIT
 */
export default {
  name: "kaiui-toast",
  data: () => ({
    /**
     * The Title
     * ***String*** (*required*)
     * `default: ''`
     */
    title: "",
    /**
     * The Time in ms
     * ***Number*** (*optional*)
     * `default: 2500`
     */
    time: 2500,
    /**
     * @private
     */
    shouldShow: false,
    /**
     * @private
     */
    timeout: false,
  }),
  methods: {
    show(title, time) {
      if (this.shouldShow && this.timeout) {
        clearTimeout(this.timeout);
      }
      if (title == null) return;

      this.title = title;
      this.shouldShow = true;
      this.timeout = setTimeout(
        () => {
          this.shouldShow = false;
        },
        time && !isNaN(time) ? time : 2500
      );
    },
  },
};
</script>

<style scoped>
.kaiui-toast {
  z-index: 9999;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--toast-background-color);
  padding: 10px;
  -webkit-box-shadow: var(--toast-box-shadow);
  -moz-box-shadow: var(--toast-box-shadow);
  box-shadow: var(--toast-box-shadow);
}

.kaiui-toast-text {
  width: 100%;
  text-align: center;
  padding: 0 10px;
  color: var(--toast-text-color);
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
