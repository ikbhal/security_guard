<script>
import { writable } from 'svelte/store';

class SecurityGuard {
	constructor(name, state, education, workingAt, mobile){
		this.name= name;
		this.state = state;
		this.mobile = mobile;
		this.education = education;
		this.workingAt = workingAt;
	}
}

var sg = new SecurityGuard("Pintu", "Odissa", "9th class", "Gopalan Mall, Bangalore");
let sgList = writable([]);

function handleSubmit() {
	console.log("handle submit");
	var sgCopy = {...sg};
	var sgListCopy = [...$sgList];
	sgListCopy.push(sgCopy);
	$sgList = sgListCopy;

	// reset sg 
	sg.name = '';
	sg.state = '';
	sg.education ='';
	sg.workingAt = '';
	console.log("sgList, ", sgList);
}
</script>

<main>

	<!-- trying https://blog.logrocket.com/how-to-use-tailwind-css-with-svelte/ --> 
	
	<!-- <add form to add security guard  -->
	
	<h1>Pintu Security Guard</h1>
	
	<div class="security_guard_preview">
		<div class="name">Name: {sg.name}</div>
		<div class="state">State: {sg.state}</div>
		<div class="education">Education: {sg.education}</div>
		<div class="working_at">Working At: {sg.workingAt}</div>
	</div>


	<hr/>

	<h3>Add SG</h3>
	<form on:submit|preventDefault={handleSubmit}>
		Name: <input type="text" bind:value={sg.name}/><br/>
		State: <input type="text" bind:value={sg.state}/><br/>
		Education: <input type="text" bind:value={sg.education}/><br/>
		Working at: <input type="text" bind:value={sg.workingAt}/><br/>
		<button type="submit">Add</button>
	</form>

	<hr/>
	<h3>Security Guard List</h3>
	<div class="security_guard_list">
		{#each $sgList as sgm}
		<div class="security_guard">
			<div class="name">{sgm.name}</div>
			<div class="state">{sgm.state}</div>
			<div class="education">{sgm.education}</div>
			<div class="working_at">{sgm.workingAt}</div>
		</div>
		{/each}
	</div>

	
</main>

<style>
main {
	padding: 10px;
}
.security_guard_preview {
	border: 1px solid grey;
}
.security_guard_list{
	border: 1px solid grey;
}
.security_guard {
	border: 1px solid grey;
	border-radius: 6px;
}
</style>