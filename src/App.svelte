<script>
  import ContactCard from "./ContactCard.svelte";

  export let name;
  let title = "";
  let image = "";
  let description = "";
  let formState = 'empty'

  function addContactCard() {
    if(
      title.trim().length === 0 ||
      image.trim().length === 0 ||
      description.trim().length === 0 ||
      formState.trim().length === 0
    ) {
      formState = 'invalid';
      return;
    }
    return formState = 'done';
  }
</script>

<style>
  #form {
    width: 30rem;
    max-width: 100%;
  }
</style>

<div id="form">
  <div class="form-control">
    <label for="userName">User Name</label>
    <input type="text" bind:value={name} id="userName" />
  </div>
  <div class="form-control">
    <label for="jobTitle">Job Title</label>
    <input type="text" bind:value={title} id="jobTitle" />
  </div>
  <div class="form-control">
    <label for="image">Image URL</label>
    <input type="text" bind:value={image} id="image" />
  </div>
  <div class="form-control">
    <label for="desc">Description</label>
    <textarea rows="3" bind:value={description} id="desc" />
  </div>
</div>

<button on:click={addContactCard}>Add Contact Card</button>

{#if formState ==='done'}

<ContactCard userName={name} jobTitle={title} {description} userImage={image} />
{:else if formState === 'invalid'}
  <p>Invalid Input</p>
{:else}
<p>Please enter some data.</p>
{/if}
