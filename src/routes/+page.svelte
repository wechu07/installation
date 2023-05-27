

<section class="section-padding">
	<div class="container">
		<div class="row">
			<div class="col-md-8 col-12">
				<h3 class="mb-4 pb-2">Pay for the installation</h3>
			</div>

			<div class="col-lg-6 col-12">
				<form action="/payment" method="post" class="custom-form contact-form">
					<div class="row">
						<div class="col-lg-12 col-12">
							<div class="form-floating">
								<input
									type="text"
									name="name"
									id="name"
									class="form-control"
									placeholder="Name"
									required=""
								/>

								<label for="floatingInput">Name</label>
							</div>
						</div>

						<div class="col-lg-12 col-12">
							<div class="form-floating">
								<select class="form-select" aria-label="Default select example">
                                    <option selected>Classification</option>
                                    <option value="1">Test</option>
                                  </select> 
							</div>

							<div class="form-floating">
								<input
									type="number"
									name="amount"
									id="amount"
									class="form-control"
									placeholder="Amount"
									required=""
								/>

								<label for="floatingTextarea">Amount</label>
							</div>
						</div>

						<div class="col-lg-4 col-12 ms-auto">
							<button type="submit" class="form-control">Submit</button>
						</div>
					</div>
				</form>
			</div>
		</div>
	</div>
</section>

<style>
	section {
		margin-top: 2em;
		padding: 0%;
	}
	button {
		background: #80d0c7;
		border-color: #7fffd4;
		border-radius: 100px;
		color: var(--white-color);
		font-family: 'Montserrat', sans-serif;
		font-size: 20px;
		font-weight: 600;
		transition: all 0.3s;
		margin-bottom: 0;
	}

	.contact-form .form-floating > textarea {
		border-radius: var(--border-radius-medium);
		height: 150px;
	}
</style>
