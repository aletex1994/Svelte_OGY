<script lang="ts" context="module">
  import type { SnackBarProps } from "./Types.svelte";
  export const Layouts = {
    'oneLine': function (props: SnackBarProps) {
      return `<div class="snackbar">${props.message}</div>`;
    },
    twoLine: function (props: SnackBarProps) {
      return `<div class="snackbar">${props.message}</div>`;
    },
    oneLineIcon: function (props: SnackBarProps) {
      return ` <div class="snackbar">
        <div class="container">
          <div class="svgBox">
            ${props.icon}
          </div>
          <div>
            <p>
              ${props.message}
            </p>
          </div>
        </div>
      </div>`;
    },
    'oneLineButton': function (props: SnackBarProps) {
      return `<div class="snackbar">
        <div class="container">
          <div class="textBox">
            <p>
             ${props.message}
            </p>
          </div>
          <div>
            <Button
            on:click=${props.action}}>
              ${props.actionText}
            </Button>
          </div>
        </div>
      </div>`;
    },
    twoLineButton: function (props: SnackBarProps) {
      return `<div class="snackbar">
        <div class="container">
          <div class="textBox">
            <p>
             ${props.message}
            </p>
          </div>
          <div>
            <Button
           on:click=${props.action}
            >
              ${props.actionText}
            </Button>
          </div>
        </div>
      </div>`;
    },
  };

  export type layoutType = keyof typeof Layouts;
</script>
