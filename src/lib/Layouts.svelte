<script lang="ts" context="module">
  import type { SnackBarProps } from "./SnackProvider.svelte";
  export const Layouts = {
    oneLine: function (props: SnackBarProps) {
      return `<div className="snackbar">${props.message}</div>`;
    },
    twoLine: function (props: SnackBarProps) {
      return `<div className="snackbar">${props.message}</div>`;
    },
    oneLineIcon: function (props: SnackBarProps) {
      return ` <div className="snackbar">
        <div className="container">
          <div className="svgBox">
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
    oneLineButton: function (props: SnackBarProps) {
      return `<div className="snackbar">
        <div className="container">
          <div className="textBox">
            <p>
             ${props.message}
            </p>
          </div>
          <div>
            <Button
              onClick={() => ${props.action()}}
            >
              ${props.actionText}
            </Button>
          </div>
        </div>
      </div>`;
    },
    twoLineButton: function (props: SnackBarProps) {
      return `<div className="snackbar">
        <div className="container">
          <div className="textBox">
            <p>
             ${props.message}
            </p>
          </div>
          <div>
            <Button
              onClick={() => ${props.action()}}
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
