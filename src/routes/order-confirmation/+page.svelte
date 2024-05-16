<script lang="ts">
	import { totalOrderValue } from '$lib/store/order';
	import CheckIcon from '$lib/icon/CheckIcon.svelte';
</script>

<span>
	<CheckIcon />
	Terimakasih atas pesanan anda sejumlah Rp {($totalOrderValue * 1000).toLocaleString('id')}!
</span>

<style>
	span {
        align-items: center;
		display: flex;
		gap: 16px;
		padding: 16px;
	}
</style>
