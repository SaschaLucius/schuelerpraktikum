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

<h1>JS</h1>

<p>
	JavaScript ist eine Programmiersprache, die verwendet wird, um Webseiten interaktiv zu machen.
</p>
<p>
	Stell dir vor, du hast ein Haus mit einem soliden Gerüst (HTML) gebaut. JavaScript ist wie die
	Elektrik und die Inneneinrichtung des Hauses.
</p>

<p>
	Es ermöglicht dir, Dinge wie Animationen, Spiele und Formulare auf deiner Webseite hinzuzufügen.
	Mit JavaScript kannst du auch auf Benutzerinteraktionen reagieren, wie zum Beispiel wenn jemand
	auf einen Button klickt oder ein Formular ausfüllt. Es hilft dabei, deine Webseite lebendig und
	funktional zu machen, ähnlich wie die verschiedenen Räume und Funktionen in einem Haus.
</p>
