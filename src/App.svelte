<script>
import ContactCard from './ContactCard.svelte';
	export let name;
	let age = 24;
	let title = '';
	let description = '';
	let image = ''
	$: upperCaseName = name.toUpperCase();

	function changeAge() {
		age = age + 1;
	}

	function changeName(e) {
		name = e.target.value
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
<!-- <button on:dblclick='{changeName}'>Change Name by Double Click</button> -->

<!-- <input type="text" value="{upperCaseName}" on:input='{changeName}' /> -->

<!-- SHortcut to above approach -->
<input placeholder="name"  type="text" bind:value="{name}">
<input placeholder="title" type="text" bind:value="{title}">
<input placeholder="iamge" type="text" bind:value="{image}">
<textarea placeholder="description" name="" id="" cols="20" rows="3" bind:value={description}></textarea>

<ContactCard userName={name} jobTitle={title} description={description} userImage={image}/>