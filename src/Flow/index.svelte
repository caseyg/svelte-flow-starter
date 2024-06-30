<script>
  import { writable } from 'svelte/store';
  import {
    SvelteFlow,
    Controls,
    Background,
    MiniMap,
    SvelteFlowProvider
  } from '@xyflow/svelte';

  // import '@xyflow/svelte/dist/style.css'
  import '@xyflow/svelte/dist/base.css';

import CustomNode from './CustomNode.svelte';
  import InputNode from './InputNode.svelte';
  
  const nodes = writable([
    {
      id: '1',
      data: { label: 'Hello' },
      position: { x: 0, y: 0 }
    },
    {
      id: '2',
      data: { label: 'World' },
      position: { x: 0, y: 150 }
    },
        {
      id: '3',
      data: { label: 'World' },
      position: { x: 250, y: 150 },
      type: 'input'
    }
  ]);

  const edges = writable([
    {
      id: '1-2',
      source: '1',
      target: '2',
    },
        {
      id: '1-3',
      source: '1',
      target: '3',
    }
  ]);

  const nodeTypes = {
    custom : CustomNode,
    input : InputNode
  }
</script>

<div style:height="100vh">
  <SvelteFlowProvider>
    <SvelteFlow snapGrid={[20,20]} {nodes} {edges} {nodeTypes} fitView>
      <Controls />
      <Background />
      <MiniMap />
    </SvelteFlow>
  </SvelteFlowProvider>
</div>