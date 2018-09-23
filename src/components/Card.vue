<template>
  <div class="card border-light">
    <h4
      v-if="hasSlot('header')"
      :class="classNamesHeader"
    >
      <slot name="header"/>
    </h4>
    <div
      v-if="hasSlot('body')"
      class="card-body"
    >
      <slot name="body"/>
    </div>
    <div
      v-if="hasSlot('footer')"
      class="card-footer bg-transparent border-0"
    >
      <slot name="footer"/>
    </div>
  </div>
</template>

<script>
/* ============
 * Card Component
 * ============
 *
 * A basic card component.
 *
 * Gives an idea how components work.
 */

import SlotMixin from '@/mixins/slot';

export default {
  /**
   * The name of the component.
   */
  name: 'Card',

  /**
   * The mixins that the component can use.
   */
  mixins: [
    SlotMixin,
  ],

  /**
   * The properties that the component accepts.
   */
  props: {
    contextualStyle: {
      default: 'primary',
      type: String,
      required: false,
    },
  },

  /**
   * The computed properties that the component can use.
   */
  computed: {
    /**
     * Computed property which will compute the classes
     * for the header of the card.
     *
     * @returns {Array} The classes for the header.
     */
    classNamesHeader() {
      const classNames = ['card-header', 'border-0'];

      if (this.contextualStyle) {
        classNames.push(`bg-${this.contextualStyle}`);
      } else {
        classNames.push('bg-default');
      }

      return classNames;
    },
  },
};
</script>

<style lang="less">
  .card-header {
    padding: 20px;
    line-height: 2;
  }

  .card {
    border: 3px solid #C3CFD9!important;
    .card-footer {
      padding-bottom: 20px;
    }
    .card-body {
      padding: 10px 20px;
      input {
        max-width: 240px;
        border: 2px solid #C3CFD9
      }
      label {
        line-height: normal!important;
      }
    }
  }

</style>
