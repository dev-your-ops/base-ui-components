<template>
  <div class="fixed z-10 inset-0 overflow-y-auto" :class="{ hidden }">
    <div class="flex items-center justify-center min-h-screen p-4">
      <div
        class="fixed inset-0 transition-opacity opacity-0 ease-in duration-300"
        aria-hidden="true"
        :class="{ 'opacity-100 ease-in duration-200': opacity }"
      >
        <div class="absolute inset-0 bg-gray-500 opacity-75"></div>
      </div>

      <span
        class="hidden inline-block align-middle h-screen"
        aria-hidden="true"
      >
        &#8203;
      </span>
      <div
        v-click-outside="close"
        class="inline-block bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all align-middle ease-in duration-200 opacity-0"
        role="dialog"
        aria-modal="true"
        aria-labelledby="modal-headline"
        :class="{ 'opacity-100 translate-y-0 sm:scale-100': opacity }"
      >
        <slot />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  methods: {
    close() {
      if (this.opacity) {
        this.$emit('close');
      }
    },
  },
  directives: {
    'click-outside': {
      bind: function (el, binding, vnode) {
        el.clickOutsideEvent = function (event) {
          // here I check that click was outside the el and his children
          if (
            !(el == event.target || el.contains(event.target)) &&
            vnode.context[binding.expression]
          ) {
            // and if it did, call method provided in attribute value
            vnode.context[binding.expression](event);
          }
        };
        document.body.addEventListener('click', el.clickOutsideEvent);
      },
      unbind: function (el) {
        document.body.removeEventListener('click', el.clickOutsideEvent);
      },
    },
  },
  watch: {
    show() {
      if (this.show) {
        this.hidden = false;
        setTimeout(() => {
          this.opacity = true;
        }, 1);
      } else {
        this.opacity = false;
        setTimeout(() => {
          if (!this.show) {
            this.hidden = true;
          }
        }, 200);
      }
    },
  },
  props: {
    show: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      hidden: !this.show,
      opacity: this.show,
    };
  },
};
</script>
