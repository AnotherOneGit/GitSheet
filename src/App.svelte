<script>
	export let UserName;
	export let ProjectName;
	export let commit;
	function sshCopy() {
		var copyText = document.getElementById("ssh");
		copyText.select();
		document.execCommand("copy");
}

	function mkdirCopy() {
		var copyText = document.getElementById("mkdir");
		copyText.select();
		document.execCommand("copy");
}

	function bareCopy() {
		var copyText = document.getElementById("bare");
		copyText.select();
		document.execCommand("copy");
}

	function cdCopy() {
		var copyText = document.getElementById("cd");
		copyText.select();
		document.execCommand("copy");
}

	function initCopy() {
		var copyText = document.getElementById("init");
		copyText.select();
		document.execCommand("copy");
}

	function remoteCopy() {
		var copyText = document.getElementById("remote");
		copyText.select();
		document.execCommand("copy");
}

	function addCopy() {
		var copyText = document.getElementById("add");
		copyText.select();
		document.execCommand("copy");
}

	function commitCopy() {
		var copyText = document.getElementById("commit");
		copyText.select();
		document.execCommand("copy");
}

	function pushCopy() {
		var copyText = document.getElementById("push");
		copyText.select();
		document.execCommand("copy");
}

</script>

<main>
	<h1>Заполните все поля и копируйте команды в консоль</h1>
	<form>
		Username: <input placeholder="Ваше имя" bind:value={UserName}>
		Projectname: <input placeholder="Имя проекта" bind:value={ProjectName}>
		Commit: <input placeholder="Введите коммит" bind:value={commit}>
	</form>
	<ol>
		<li>
			<input readonly id="ssh" value="https://github.com">
			<button class="waves-effect waves-light btn-small" on:click={sshCopy}>Copy</button>

			<input readonly id="bare" value="git init --bare">
			<button class="waves-effect waves-light btn-small" on:click={bareCopy}>Copy</button>
		</li>
	<h3>На локальной машине, в папке проекта:</h3>
		<li>
			<input readonly id="init" value="git init">
			<button class="waves-effect waves-light btn-small" on:click={initCopy}>Copy</button>
		</li>
		<li>
			<input readonly id="remote" value="git remote add origin https://github.com/{UserName}/{ProjectName}.git">
			<button class="waves-effect waves-light btn-small" on:click={remoteCopy}>Copy</button>
		</li>
		<li>
			<input readonly id="add" value="git add .">
			<button class="waves-effect waves-light btn-small" on:click={addCopy}>Copy</button>
		</li>
		<li>
			<input readonly id="commit" value="git commit -m '{commit}'">
			<button class="waves-effect waves-light btn-small" on:click={commitCopy}>Copy</button>
		</li>
		<li>
			<input readonly id="push" value="git push origin master">
			<button class="waves-effect waves-light btn-small" on:click={pushCopy}>Copy</button>
		</li>
	</ol>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		background: linear-gradient(to right, #667db6, #0082c8, #0082c8, #667db6);
	}

	h1 {
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>