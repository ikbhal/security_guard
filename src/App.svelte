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
	
	<div class="">
		<h3>Add SG</h3>
		<form
			class = "bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4"	
			on:submit|preventDefault={handleSubmit}>

			<div class="mb-4">
  				<label class="block text-gray-700 text-sm font-bold mb-2" for="name">
        		Name
      			</label>
      			<input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
				   id="name" type="text" placeholder="Name" 
				   bind:value={sg.name}>
    		</div>

			<div class="mb-4">
  				<label class="block text-gray-700 text-sm font-bold mb-2" for="state">
        		State
      			</label>
      			<input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
				   id="state" type="text" placeholder="State" 
				   bind:value={sg.state}>
    		</div>
			
			<div class="mb-4">
  				<label class="block text-gray-700 text-sm font-bold mb-2" for="education">
				Education
      			</label>
      			<input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
				   id="education" type="text" placeholder="Education" 
				   bind:value={sg.education}>
    		</div>

			<div class="mb-4">
  				<label class="block text-gray-700 text-sm font-bold mb-2" for="workingAt">
				Working At
      			</label>
      			<input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
				   id="workingAt" type="text" placeholder="Working At" 
				   bind:value={sg.workgingAt}>
    		</div>
			<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
				type="submit">Add</button>
		</form>
	</div>

	<hr/>
	<h3>Security Guard List</h3>
	<div class="security_guard_list">
		{#each $sgList as sgm}
		<div class="rounded overflow-hidden shadow-lg">
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
/* .security_guard {
	border: 1px solid grey;
	border-radius: 6px;
} */
</style>