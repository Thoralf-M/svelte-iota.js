<script>
  import { composeAPI } from "@iota/core";

  let iotanode = "https://nodes.thetangle.org:443";

  getNodeInfo();
  function getNodeInfo() {
    let iota = composeAPI({
      provider: iotanode
    });

    iota
      .getNodeInfo()
      .then(info => {
        nodeinfo = JSON.stringify(info, null, 1);
        console.log(info);
      })
      .catch(err => {
        nodeinfo = err.message;
        console.log(err);
      });
  }

  export let nodeinfo;
</script>

<style>
  pre {
    color: purple;
  }
  input {
    width: 300px;
  }
</style>

<input
  bind:value={iotanode}
  on:input={getNodeInfo}
  placeholder="https://nodes.thetangle.org:443" />

<pre>Nodeinfo: {nodeinfo}</pre>
