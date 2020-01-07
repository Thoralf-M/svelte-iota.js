<script>
import { composeAPI } from '@iota/core'

let iota = composeAPI({
      provider: 'https://community.tanglebay.org'
})


iota.getNodeInfo()
    .then(info => {
			nodeinfo = JSON.stringify(info, null, 1)
			console.log(info)}
			)
		.catch(err => console.log(err))

	export let nodeinfo;
</script>

<style>
	pre {
		color: purple;
	}
</style>

<pre>Nodeinfo: {nodeinfo}</pre>