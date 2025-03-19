<script lang="ts">
	import { page } from '$app/stores';

	import Chat from '$lib/components/chat/Chat.svelte';
	import Help from '$lib/components/layout/Help.svelte';
</script>

{#if 0> 1}
<Help />
{/if}
<Chat chatIdProp={$page.params.id} />
