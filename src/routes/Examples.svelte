<script>
	import { ripple } from "$lib";
	import CodeBlock from "./CodeBlock.svelte";
	import { CODE } from "./example";
</script>

<div use:ripple class="box imgripple">Image ripple</div>
<div use:ripple class="box gradient">Gradient ripple</div>

<br />
<br />

<p>Needs to be wrapped in a div for void elements like img, input, etc.</p>

<div use:ripple class="imgbox">
	<img
		src="https://images.unsplash.com/photo-1518546305927-5a555bb7020d?w=400&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8Yml0Y29pbnxlbnwwfHwwfHx8MA%3D%3D"
		alt="Man dancing"
	/>
</div>

<div
	use:ripple={{
		color: "rgba(0,0,0,0.5)",
	}}
>
	<input type="text" placeholder="Type something" style="width: 100%;" />
</div>

<br /><br />

<CodeBlock code={CODE} />

<style>
	.box {
		height: 200px;
		width: 200px;
		align-items: center;
		justify-content: center;
		border: 1px solid black;
		border-radius: 5px;
		margin-top: 20px;
		margin-right: 20px;
		display: inline-flex;
		user-select: none;
	}

	.imgbox {
		height: 200px;
		width: 200px;
		border-radius: 5px;
		margin-top: 20px;
		margin-right: 20px;
		display: inline-flex;
	}

	.imgbox img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	:global(.imgripple .ripple) {
		background: url(https://media.tenor.com/VFFJ8Ei3C2IAAAAM/rickroll-rick.gif);
		background-size: 80%;
		background-position: center;
		background-repeat: no-repeat;
		z-index: -1;
	}

	:global(.gradient .ripple) {
		background: linear-gradient(45deg, #f3ed783d, #af4261);
	}
</style>
