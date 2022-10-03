<script lang="ts" context="module">
  import OneLine from "./Layouts/OneLine.svelte";
  import TwoLines from "./Layouts/twoLines.svelte";
  import OneLineIcon from "./Layouts/OneLineIcon.svelte";
  import OneLineButton from "./Layouts/oneLineButton.svelte";
  import TwoLinesButton from "./Layouts/twoLinesButton.svelte";
  export const Layouts = {
    oneLine: OneLine,
    twoLines: TwoLines,
    oneLineIcon: OneLineIcon,
    oneLineButton: OneLineButton,
    twoLinesButton: TwoLinesButton,
  };
  
  export type layoutType = keyof typeof Layouts;

</script>