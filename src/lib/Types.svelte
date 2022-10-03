<script lang="ts" context="module">
    import type { Writable } from "svelte/store";
    import type { layoutType } from "./Layout.svelte";
    import type { positionType } from "./Positions.svelte";
  
    // Type for Snack
    export type SnackBarType = {
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
      snackBarArray?: Writable<SnackBarType[]> | undefined;
      addSnackBar: (snackbar: SnackBarType) => void;
    };
    // Type for SnackProvider
    export type SnackProviderType = {
      durationms?: number;
      maxSnack?: number;
      position?: positionType;
    };
  </script>