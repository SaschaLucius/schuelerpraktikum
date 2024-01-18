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

<h1>Taschenrechner V1</h1>

<input bind:value={input} type="text" />

<button on:click={() => add(7)}>7</button>
<button on:click={() => add(8)}>8</button>
<button on:click={() => add(9)}>9</button>
<button on:click={() => add('+')}>+</button>
<button on:click={() => add(4)}>4</button>
<button on:click={() => add(5)}>5</button>
<button on:click={() => add(6)}>6</button>
<button on:click={() => add('-')}>-</button>
<button on:click={() => add(1)}>1</button>
<button on:click={() => add(2)}>2</button>
<button on:click={() => add(3)}>3</button>
<button on:click={() => add('*')}>*</button>
<button on:click={() => add(0)}>0</button>
<button on:click={() => add('.')}>.</button>
<button on:click={() => clear()}>C</button>
<button on:click={() => add('/')}>/</button>
<button on:click={() => equals()}>=</button>
