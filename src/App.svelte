<script>
	export let name;
	let age = 24;
	function changeAge() {
		age = age + 1;
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}!</h1>
<h2>My age is {age}</h2>
<button on:click='{changeAge}'>Change Age</button>
