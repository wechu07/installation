<script>
	import { onMount, afterUpdate } from 'svelte';

	let name = '';
	let phone = '';
	let classification = '';
	let price = '';

	const classifications = [
		{ value: '', label: 'Select Classification' },
		{ value: 'test', label: 'Test' },
		{ value: 'rotaractor', label: 'Rotaractor' },
		{ value: 'rotarian', label: 'Rotarian' }
	];

	function handleSubmit() {
		// Perform API call and payment processing here
		// Display payment status message upon completion
		const paymentStatus = document.getElementById('paymentStatus');
		paymentStatus.innerText = 'Payment Complete!';
	}

	function updatePrice() {
		switch (classification) {
			case 'test':
				price = 'KES 1';
				break;
			case 'rotaractor':
				price = 'KES 1500';
				break;
			case 'rotarian':
				price = 'KES 2000';
				break;
			default:
				price = '';
				break;
		}
	}

	onMount(() => {
		updatePrice();
	});

	afterUpdate(() => {
		updatePrice();
	});
</script>

<main>
	<form on:submit={handleSubmit}>
		<label for="name">Name</label>
		<input type="text" id="name" bind:value={name} required />

		<label for="phone">Phone Number</label>
		<input type="tel" id="phone" bind:value={phone} required />

		<label for="classification">Classification</label>
		<select id="classification" bind:value={classification} required>
			{#each classifications as { value, label }}
				<option {value}>{label}</option>
			{/each}
		</select>

		<label for="price">Price</label>
		<input type="text" id="price" bind:value={price} readonly />

		<button type="submit">Submit</button>
	</form>
	<div id="paymentStatus" />
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 20px;
	}

	form {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 300px;
		padding: 20px;
		background-color: #fff;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
	}

	form label {
		font-weight: bold;
		margin-bottom: 5px;
	}

	form input,
	form select {
		width: 100%;
		padding: 10px;
		margin-bottom: 10px;
		border: 1px solid #ccc;
		border-radius: 4px;
	}

	form button {
		padding: 10px 20px;
		background-color: #4caf50;
		color: white;
		border: none;
		border-radius: 4px;
		cursor: pointer;
	}

	#paymentStatus {
		margin-top: 20px;
		text-align: center;
	}
</style>
