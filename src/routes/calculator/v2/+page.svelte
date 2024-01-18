<script lang="ts">
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

<h1>Taschenrechner V2</h1>

<div class="calculator">
	<input bind:value={input} type="text" class="display" />
	<div class="buttons">
		<button on:click={() => add(7)}>7</button>
		<button on:click={() => add(8)}>8</button>
		<button on:click={() => add(9)}>9</button>
		<button on:click={() => add('+')} class="operator">+</button>
		<button on:click={() => add(4)}>4</button>
		<button on:click={() => add(5)}>5</button>
		<button on:click={() => add(6)}>6</button>
		<button on:click={() => add('-')} class="operator">-</button>
		<button on:click={() => add(1)}>1</button>
		<button on:click={() => add(2)}>2</button>
		<button on:click={() => add(3)}>3</button>
		<button on:click={() => add('*')} class="operator">*</button>
		<button on:click={() => add(0)}>0</button>
		<button on:click={() => add('.')}>.</button>
		<button on:click={() => clear()} class="clear">C</button>
		<button on:click={() => add('/')} class="operator">/</button>
		<button on:click={() => equals()} class="equals">=</button>
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

	button {
		padding: 10px;
		font-size: 18px;
		border: none;
		cursor: pointer;
		border-radius: 5px;
		text-align: center;
	}

	.operator {
		border: 0px solid #a46d19;
		background: #f90;
	}
	.clear {
		border: 0px solid #000;
		background: red;
	}
	.equals {
		border: 0px solid #000;
		background: #245be9;
		width: 320px;
	}
</style>
