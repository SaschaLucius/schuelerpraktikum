<script lang="ts">
	import Button from './Button.svelte';

	let input = '';

	function add(text: string | number) {
		input += text;
	}
	function clear() {
		input = '';
	}
	function equals() {
		input = eval(input);
	}
</script>

<div class="calculator">
	<input bind:value={input} type="text" class="display" />
	<div class="buttons">
		<Button input={7} clicked={(i) => add(i)} />
		<Button input={8} clicked={(i) => add(i)} />
		<Button input={9} clicked={(i) => add(i)} />
		<Button input={'+'} clicked={(i) => add(i)} type="operator" />
		<Button input={4} clicked={(i) => add(i)} />
		<Button input={5} clicked={(i) => add(i)} />
		<Button input={6} clicked={(i) => add(i)} />
		<Button input={'-'} clicked={(i) => add(i)} type="operator" />
		<Button input={1} clicked={(i) => add(i)} />
		<Button input={2} clicked={(i) => add(i)} />
		<Button input={3} clicked={(i) => add(i)} />
		<Button input={'*'} clicked={(i) => add(i)} type="operator" />
		<Button input={0} clicked={(i) => add(i)} />
		<Button input={'.'} clicked={(i) => add(i)} />
		<Button input={'C'} clicked={() => clear()} type="clear" />
		<Button input={'/'} clicked={(i) => add(i)} type="operator" />
		<Button input={'='} clicked={() => equals()} type="equals" />
	</div>
</div>

<style>
	.calculator {
		display: inline-block;
		border: 1px solid #ccc;
		padding: 10px;
		border-radius: 5px;
		box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
	}

	.display {
		font-size: 24px;
		border: 1px solid #ccc;
		height: 24px;
		padding: 10px;
		margin-bottom: 10px;
		width: 300px;
		text-align: right;
	}

	.buttons {
		display: grid;
		grid-template-columns: repeat(4, 75px);
		gap: 5px;
	}
</style>
