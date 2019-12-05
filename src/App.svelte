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

<main class="container row">
  <div class="navbar-fixed">
    <nav class="container">
      <div class="nav-wrapper">
        <ul>
          <li><a href="sass.html">Start</a></li>
          <li><a href="badges.html">Clone</a></li>
        </ul>
      </div>
    </nav>
  </div>
	<h1>Заполните все поля и копируйте команды в консоль</h1>
	<div class="row">
		<form class="col s12">
			<div class="row">
				<div class="input-field col s6">
					<label for="username">Username:</label><br>
					<input id="username" placeholder="Ваше имя" bind:value={UserName}>
				</div>
				<div class="input-field col s6">
					<label for="projectname">Projectname:</label><br>
					<input id="projectname" placeholder="Имя проекта" bind:value={ProjectName}>
				</div>
				<div class="input-field col s12">
					<label for="commit">Commit:</label><br>
					<input id="commit" placeholder="Введите коммит" bind:value={commit}>
				</div>
			</div>
		</form>
	</div>
	<ol>
		<li>
			<input readonly id="init" value="git init">
			<button class="waves-effect waves-light btn-small" on:click={initCopy}>Copy</button>
		</li>
		<li>
			<input readonly id="remote" value="git remote add origin https://github.com/{UserName}/{ProjectName}">
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