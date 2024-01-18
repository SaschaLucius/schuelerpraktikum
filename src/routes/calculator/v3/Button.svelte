<script lang="ts">
	export let input: string | number;
	export let clicked = (input: string | number) => {
		console.log('I am being clicked: ' + input);
	};
	export let type: string = 'normal';

	const typeToColor = new Map();
	typeToColor.set('clear', 'red');
	typeToColor.set('equals', '#245be9');
	typeToColor.set('operator', '#f90');
	typeToColor.set('normal', '#f0f0f0');
</script>

<button
	on:click={() => clicked(input)}
	style="background-color:{typeToColor.get(type)}; {type === 'equals' ? 'width: 320px;' : ''}"
	>{input}</button
>

<style>
	button {
		padding: 10px;
		font-size: 18px;
		border: none;
		cursor: pointer;
		border-radius: 5px;
		text-align: center;
	}
</style>
