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

	<!-- trying https://blog.logrocket.com/how-to-use-tailwind-css-with-svelte/ --> 
	
	<!-- <add form to add security guard  -->
	
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