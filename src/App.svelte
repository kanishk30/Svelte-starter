<script>
	export let name;
	let age = 24;
	$: upperCaseName = name.toUpperCase();

	function changeAge() {
		age = age + 1;
	}

	function changeName() {
		name = 'Kanishk Agrawal';
	}

</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {upperCaseName}!</h1>
<h2>My age is {age}</h2>
<button on:click='{changeAge}'>Change Age</button>
<button on:dblclick='{changeName}'>Change Name by Double Click</button>
