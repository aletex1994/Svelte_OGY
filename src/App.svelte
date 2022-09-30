<script lang="ts">
  import svelteLogo from "./assets/svelte.svg";
  import { writable } from "svelte/store";
  import { setContext } from "svelte";
  import AppProvider from "./lib/AppProvider.svelte";
  import type { SnackBarProps, ContextType } from "./lib/Types.svelte";

  let isOpen = writable(false);
  let snackBarArray = writable<SnackBarProps[]>([]);
  const addSnackBar = (snackbar: SnackBarProps) => {
    isOpen.set(true);
    // add the snackbar to snackBarArray
    snackBarArray.update((arr) => [...arr, snackbar]);
    console.log($snackBarArray);
  };
  // set the context
  setContext<ContextType>("snackContext", {
    isOpen,
    snackBarArray,
    addSnackBar,
    providerPosition: "bottom-right",
  });
</script>
<main>
  <AppProvider maxSnack={3} durationms={3000} position={"top-right"}>
    <div>
      <button
        on:click={() =>
          addSnackBar({
            layout: "oneLine",
            message: "This is a One Line Snack",
          })}>Stack One Line Snack</button
      >
      <button
      on:click={() =>
        addSnackBar({
          layout: "twoLines",
          message: "This is a One Line Snack,Stack Two Lines Snack,Stack Two Lines Snack,Stack Two Lines Snack",
        })}>Stack Two Lines Snack</button
    >
    <button
    on:click={() =>
      addSnackBar({
        layout: "oneLineIcon",
        message: "This is a One Line Snack",
        icon: svelteLogo,
      })}>Stack Icon Snack</button
  >
  <button
  on:click={() =>
    addSnackBar({
      layout: "oneLineButton",
      message: "This is a One Line Snack with Button",
      actionText: "Click Me",
      action: () => {
        alert("Button Clicked");
      },
    })}>Stack One Line Button Snack</button
>
<button
on:click={() =>
  addSnackBar({
    layout: "twoLinesButton",
    message: "This is a One Line Snack with Button, This is a One Line Snack,Stack Two Lines Snack,Stack Two Lines Snack,Stack Two Lines Snack, This is a One Line Snack,Stack Two Lines Snack,Stack Two Lines Snack,Stack Two Lines Snack",
    actionText: "Click Me",
    action: () => {
      alert("Button Clicked");
    },
  })}>Stack two Lines Button Snack</button
>

    </div>
  </AppProvider>
</main>
