<template>
  <main>
    <div ref="graphContainer"></div>
  </main>
</template>

<script>
import ForceGraph3D from "3d-force-graph";

export default {
  data() {
    return {
      nodes: [
        {
          id: "id1",
          name: "name1",
          val: 1,
        },
        {
          id: "id2",
          name: "name2",
          val: 10,
        },
      ],
    };
  },
  mounted() {
    // Create an instance of 3D Force Graph
    const graph = ForceGraph3D()(this.$refs.graphContainer)
      .nodeLabel("id")
      .nodeAutoColorBy("group")
      .onNodeDragEnd((node) => {
        node.fx = node.x;
        node.fy = node.y;
        node.fz = node.z;
      })
      .width(1080)
      .height(500)

    // Define your graphData here (nodes and links)
    const nodes = [
      { id: 'A', group: 1 },
      { id: 'B', group: 2 },
      { id: 'C', group: 3 },
      // Add more nodes as needed
    ];

    const links = [
      { source: 'A', target: 'B' },
      { source: 'B', target: 'C' },
      { source: 'C', target: 'A' },
      // Add more links as needed
    ];

    // Set the graphData
    graph.graphData({
      nodes,
      links,
    })
  },
};
</script>