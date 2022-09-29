<script lang="ts" context="module">
  import type { layoutType } from "./Layouts.svelte";
  import type { positionType } from "./Positions.svelte";

  // Type for Snack
  export type SnackBarProps = {
    layout: layoutType;
    message: string;
    icon?: any;
    actionText?: string;
    action?: Function;
    snackPosition?: positionType;
  };
  // Type for Context
  export type ContextType = {
    isOpen: boolean;
    snackBarArray?: SnackBarProps[];
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
