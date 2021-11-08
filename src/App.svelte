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
	
	<h1>Pintu Security Guard</h1>
	
	<div class="security_guard">
		<div class="name">{sg.name}</div>
		<div class="state">{sg.state}</div>
		<div class="education">{sg.education}</div>
		<div class="working_at">{sg.workingAt}</div>
	</div>

	<hr/>
	<h3>Todo app with tailwind css</h3>
	<div class="h-100 w-full flex items-center justify-center bg-teal-lightest font-sans">
	<div class="bg-white rounded shadow p-6 m-4 w-full lg:w-3/4 lg:max-w-lg">
        <div class="mb-4">
            <h1 class="text-grey-darkest">Todo List</h1>
            <div class="flex mt-4">
                <input class="shadow appearance-none border rounded w-full py-2 px-3 mr-4 text-grey-darker" placeholder="Add Todo">
                <button class="flex-no-shrink p-2 border-2 rounded text-teal border-teal hover:text-white hover:bg-teal">Add</button>
            </div>
        </div>
        <div>
            <div class="flex mb-4 items-center">
                <p class="w-full text-grey-darkest">Add another component to Tailwind Components</p>
                <button class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-white text-green border-green hover:bg-green">Done</button>
                <button class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-white hover:bg-red">Remove</button>
            </div>
          	<div class="flex mb-4 items-center">
                <p class="w-full line-through text-green">Submit Todo App Component to Tailwind Components</p>
                <button class="flex-no-shrink p-2 ml-4 mr-2 border-2 rounded hover:text-white text-grey border-grey hover:bg-grey">Not Done</button>
                <button class="flex-no-shrink p-2 ml-2 border-2 rounded text-red border-red hover:text-white hover:bg-red">Remove</button>
            </div>
        </div>
    </div>
</div>
</main>

<style>
</style>