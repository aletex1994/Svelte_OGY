<script lang="ts" context="module">
  import type { SnackBarProps } from "./Types.svelte";
  export const Layouts = {
    // One Line Layout
    oneLine: (props: SnackBarProps) => {
      return '<div class="snackbar">' + props.message + "</div>";
    },
    twoLine: (props: SnackBarProps) => {
      return '<div class="snackbar">' + props.message + "</div>";
    },
    oneLineIcon: (props: SnackBarProps) => {
      return (
        '<div class="snackbar"><div class="container"><div class="svgBox"><img src='+
          props.icon +
           ' height="16px" width="16px"></div><div><p>'+props.message+'</p></div></div></div>'

      );
    },
  }
  //   'twoLine': function (props: SnackBarProps) {
  //     return `<div class="snackbar">${props.message}</div>`;
  //   },
  //   'oneLineIcon': function (props: SnackBarProps) {
  //     return ` <div class="snackbar">
  //       <div class="container">
  //         <div class="svgBox">
  //           ${props.icon}
  //         </div>
  //         <div>
  //           <p>
  //             ${props.message}
  //           </p>
  //         </div>
  //       </div>
  //     </div>`;
  //   },
  //   'oneLineButton': function (props: SnackBarProps) {
  //     return `<div class="snackbar">
  //       <div class="container">
  //         <div class="textBox">
  //           <p>
  //            ${props.message}
  //           </p>
  //         </div>
  //         <div>
  //           <Button
  //           on:click=${props.action}}>
  //             ${props.actionText}
  //           </Button>
  //         </div>
  //       </div>
  //     </div>`;
  //   },
  //   'twoLineButton': function (props: SnackBarProps) {
  //     return `<div class="snackbar">
  //       <div class="container">
  //         <div class="textBox">
  //           <p>
  //            ${props.message}
  //           </p>
  //         </div>
  //         <div>
  //           <Button
  //          on:click=${props.action}
  //           >
  //             ${props.actionText}
  //           </Button>
  //         </div>
  //       </div>
  //     </div>`;
  //   },
  // };

  export type layoutType = keyof typeof Layouts;
</script>
