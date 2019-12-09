<script>
	export let UserName;
	export let ProjectName;
	export let commit;
	function Copy(){
		let id = this.id;
		let copyText = document.getElementById(id);
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
			<button id="init" class="waves-effect waves-light btn-small" on:click={Copy}>Copy</button>
		</li>
		<li>
			<input readonly id="remote" value="git remote add origin https://github.com/{UserName}/{ProjectName}">
			<button id="remote" class="waves-effect waves-light btn-small" on:click={Copy}>Copy</button>
		</li>
		<li>
			<input readonly id="add" value="git add .">
			<button id="add" class="waves-effect waves-light btn-small" on:click={Copy}>Copy</button>
		</li>
		<li>
			<input readonly id="commit" value="git commit -m '{commit}'">
			<button id="commit" class="waves-effect waves-light btn-small" on:click={Copy}>Copy</button>
		</li>
		<li>
			<input readonly id="push" value="git push origin master">
			<button id="push" class="waves-effect waves-light btn-small" on:click={Copy}>Copy</button>
		</li>
	</ol>
</main>	