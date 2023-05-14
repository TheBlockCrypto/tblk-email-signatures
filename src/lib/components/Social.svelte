<script lang="ts">
	export let logo = '';
	export let url = '';
	export let alt = '';
</script>

{#if url}
	<td style="padding-right: 12px;"
		><a href={url} target="_blank"><img width="40" {alt} border="0" src={logo} /></a>
	</td>
{/if}
