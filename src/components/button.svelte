<script context="module" lang="ts">
  export enum ButtonSize {
    XSMALL = 'xsmall',
    SMALL = 'small',
    MEDIUM = 'medium',
    LARGE = 'large',
    XLARGE = 'xlarge'
  };

  export enum ButtonStyle {
    PRIMARY = 'primary',
    SECONDARY = 'secondary'
  }
</script>

<script lang="ts">  
  export let lable;
  export let type = 'button';

  // Button style
  export let style: ButtonStyle = ButtonStyle.PRIMARY;

  // Button state
  export let disabled = false;

  // Button size
  export let size: ButtonSize = ButtonSize.MEDIUM;
</script>

<button type={type} class={`${size} ${style}`} disabled={disabled}>{lable}</button>

<style>
  /** @TOOD: remeber to remove the indego color in favor of the primary color */
  .primary {
    @apply inline-flex items-center rounded-md border border-transparent text-sm font-medium text-white shadow-sm bg-indigo-600;
  }

  .primary:focus {
    @apply outline-none ring-2 ring-indigo-500 ring-offset-2;
  }

  .primary:hover {
    @apply bg-indigo-700;
  }

  .secondary {
    @apply inline-flex items-center rounded border border-gray-300 bg-white px-2.5 py-1.5 text-xs font-medium text-gray-700 shadow-sm;
  }

  .secondary:focus {
    @apply outline-none ring-2 ring-indigo-500 ring-offset-2;
  }

  .secondary:hover {
    @apply bg-gray-50;
  }

  .xsmall {
    @apply px-2.5 py-1.5 text-xs;
  }

  .small {
    @apply px-3 py-2 text-sm;
  }

  .medium {
    @apply px-4 py-2 text-sm;
  }

  .large {
    @apply px-4 py-2 text-base;
  }

  .xlarge {
    @apply px-6 py-3 text-base;
  }
</style>
