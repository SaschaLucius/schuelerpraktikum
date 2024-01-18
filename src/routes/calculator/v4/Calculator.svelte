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

	function keyPressed(event: KeyboardEvent) {
		switch (event.key) {
			case 'Enter':
				equals();
				break;
			case '0':
				add('0');
				break;
			case '1':
				add('1');
				break;
			case '2':
				add('2');
				break;
			case '3':
				add('3');
				break;
			case '4':
				add('4');
				break;
			case '5':
				add('5');
				break;
			case '6':
				add('6');
				break;
			case '7':
				add('7');
				break;
			case '8':
				add('8');
				break;
			case '9':
				add('9');
				break;
			case '.':
				add('.');
				break;
			case '+':
				add('+');
				break;
			case '-':
				add('-');
				break;
			case '*':
				add('*');
				break;
			case '/':
				add('/');
				break;
			case 'c':
				clear();
				break;
		}
	}
</script>

<svelte:window on:keydown|preventDefault={(event) => keyPressed(event)} />

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
