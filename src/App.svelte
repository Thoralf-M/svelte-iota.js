<script>
  import { composeAPI } from "@iota/core";

  let iotanode = "https://community.tanglebay.org";

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
  placeholder="https://community.tanglebay.org" />

<pre>Nodeinfo: {nodeinfo}</pre>
