<script lang="ts">
	import MinusIcon from '$lib/icon/MinusIcon.svelte';
	import PlusIcon from '$lib/icon/PlusIcon.svelte';
	import { order } from '$lib/store/order';

	$: counter = $order[menuId + '_' + id] ?? 0;

	export let menuId: string;
	export let id: string;
	export let label: string;
	export let price: number;

	const add = () => {
		$order[menuId + '_' + id] = counter + 1;
	};

	const substract = () => {
		if (!$order[menuId + '_' + id]) return;
		$order[menuId + '_' + id] = counter - 1;
	};
</script>

<div class="menu-price-row">
	<span class="price-description">{label}</span>
	<span class="price-value">{price}</span>
	<div class="menu-controls">
		<button on:click={substract}><MinusIcon /></button>
		<span>{counter}</span>
		<button on:click={add}><PlusIcon /></button>
	</div>
</div>

<style>
	div.menu-price-row {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		padding: 0 16px;

		gap: 16px;
	}

	span.price-description {
		font-size: 12px;
	}

	span.price-value {
		flex: 1;
		text-align: end;
	}

	div.menu-controls {
		display: flex;
		flex-direction: row;
		gap: 4px;
	}
</style>
