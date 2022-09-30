<script lang="ts" context="module">
  import type { Writable } from "svelte/store";
  import type { layoutType } from "./Layout.svelte";
  import type { positionType } from "./Positions.svelte";

  // Type for Snack
  export type SnackBarProps = {
    layout: layoutType;
    message: string;
    icon?: any;
    actionText?: any;
    action?: Function;
    snackPosition?: positionType;
  };
  // Type for Context
  export type ContextType = {
    isOpen: Writable<boolean>;
    snackBarArray?: Writable<SnackBarProps[]> | undefined;
    addSnackBar: (snackbar: SnackBarProps) => void;
    providerPosition: positionType;
  };
  // Type for SnackProvider
  export type SnackProviderProps = {
    durationms?: number;
    maxSnack?: number;
    position?: positionType;
  };
</script>
