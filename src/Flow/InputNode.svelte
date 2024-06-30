<script>
  import { Handle, Position } from '@xyflow/svelte';

  export let positionAbsolute = { x:0, y:0 };
</script>

<Handle type="target" position={Position.Left} />

<textarea oninput='this.style.height = "";this.style.height = this.scrollHeight + "px"'/>

<Handle type="source" position={Position.Right} />

<style>
textarea {
  resize: none;
  border: none;
}
</style>