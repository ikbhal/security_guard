<script>
class SecurityGuard {
	// constructor(name){
	// 	this.name = name;
	// }
	// constructor(workingAt){
	// 	this.workingAt = workingAt;
	// }
	// constructor(state){
	// 	this.state = state;
	// }
	// constructor(name, state){
	// 	this.name = name;
	// 	this.state = state;
	// }
	constructor(name, state, mobile, education, workingAt){
		this.name= name;
		this.state = state;
		this.mobile = mobile;
		this.education = education;
		this.workingAt = workingAt;
	}
}

var sg = new SecurityGuard("Pintu", "Odissa", "9th class", "Gopalan Mall, Bangalore");

</script>

<main>
	<!-- tail wind css cdn -->
	<!-- <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.css" integrity="sha512-wnea99uKIC3TJF7v4eKk4Y+lMz2Mklv18+r4na2Gn1abDRPPOeef95xTzdwGD9e6zXJBteMIhZ1+68QC5byJZw==" crossorigin="anonymous" referrerpolicy="no-referrer" /> -->


	<!-- trying https://blog.logrocket.com/how-to-use-tailwind-css-with-svelte/ -->

	<h1 class="py-8 px-4 border border-indigo-900 shadow-lg">Hello {name}!</h1>
  	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	
	<h1>Pintu Security Guard</h1>
	
	<div class="security_guard">
		<div class="name">{sg.name}</div>
		<div class="state">{sg.state}</div>
		<div class="education">{sg.education}</div>
		<div class="working_at">{sg.workingAt}</div>
	</div>
</main>

<style>
</style>