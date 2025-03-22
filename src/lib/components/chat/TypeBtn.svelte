<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import type { TypeBtnInfo } from '$lib/stores';

	const dispatch = createEventDispatcher();

	export let btnInfo: TypeBtnInfo;

	export let activeId: string;

	const handClick = () => {
		dispatch('changeType', btnInfo);
	};
</script>

<button
	type="button"
	class="type-btn flex items-center {activeId === btnInfo.id ? 'btn-active' : ''}"
	on:click={handClick}
>
	{#if btnInfo.icon}
		<img class="btn-icon" src={btnInfo.icon} alt="" />
	{/if}
	<div class="btn-txt">{btnInfo.name}</div>
</button>

<style>
	.type-btn {
		/* display: flex;
    align-items: center; */
		padding: 2px 22px;
		border: 1px solid #dfe0e3;
		border-radius: 30px;
		font-size: 14px;
		height: 40px;
		line-height: 14px;
		background-color: #fff;
		color: #666;
		&:not(:last-child) {
			margin-right: 10px;
		}
	}
	.btn-active {
		color: #1286f8;
		border-color: #1286f8;
	}
	.btn-icon {
		display: block;
		width: 24px;
		height: 24px;
		margin-right: 5px;
	}
	.btn-txt {
		height: 24px;
		line-height: 24px;
	}
</style>
