
<script lang="ts">
	type Action = "decrease" | "increase" | "reset";

	let count = $state(0);

	function handleClick(action: Action) {
		switch (action) {
			case "decrease":
				count--;
				break;

			case "increase":
				count++;
				break;

			case "reset":
				count = 0;
				break;
		}
	}

	let color = $derived(
		count > 0 ? "green" :
		count < 0 ? "red" :
		"black"
	);
</script>

<div class="container">
	<header>
		<h1>Counter</h1>
	</header>

	<main>
		<section>
			<p id="value" style:color={color}>
				{count}
			</p>

			<section class="button-container">
				<button
					class="btn decrease"
					onclick={() => handleClick("decrease")}
				>
					decrease
				</button>

				<button
					class="btn reset"
					onclick={() => handleClick("reset")}
				>
					reset
				</button>

				<button
					class="btn increase"
					onclick={() => handleClick("increase")}
				>
					increase
				</button>
			</section>
		</section>
	</main>
</div>


