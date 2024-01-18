<script lang="ts">
	let account = 'dtmr-plat-gbl-dev';
	let user = 'dev';
	let value = '';

	$: href = `https://signin.aws.amazon.com/switchrole?displayName=${account}-${user}&roleName=${account}-${user}&account=${account}`;

	let accounts = ['dev', 'production'];

	function openLink() {
		window.open(href, '_blank');
	}
</script>

<h1>Configurator V0</h1>

<label for="account">Choose a account:</label>

<select bind:value={account} name="account" id="account">
	{#each accounts as account}
		<option value={account}>{account}</option>
	{/each}
</select>

<label for="user">Choose a user:</label>

<select bind:value={user} name="user" id="user">
	<option value="admin">Admin</option>
	<option value="poweruser">Poweruser</option>
	<option value="dev">Dev</option>
</select>

<br />

<button on:click={() => openLink()}>{account + '-' + user}</button>
