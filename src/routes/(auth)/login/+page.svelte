<script>
	let email = '';
	let password = '';

	function handleLogin() {
		// Handle login logic here
	}
</script>

<main class="flex justify-center items-center h-screen">

	<div class="container mx-auto flex justify-center items-center">
		<div class="columns">
			<div class="column col-12 col-md-8 col-mx-auto my-5">
				<!-- Use col-12 for full width on mobile and col-md-8 for larger screens -->

				<div class="card p-3 mx-auto min-h-[480px] min-w-[640px] flex flex-col justify-center items-center space-y-8">
					<!-- Added "mx-auto" class for horizontal centering -->
					<div class="card-header mb-4">
						<h4 class="card-title">Login</h4>
					</div>

					<div class="card-body flex flex-col space-y-8">

						<div class="form-group">
							<!-- Added "mb-3" class for margin-bottom -->
							<label class="form-label mb-1" for="email">Email</label>
							<input
								class="form-input"
								type="email"
								id="email"
								bind:value={email}
								placeholder="Enter your email"
							/>
						</div>

						<div class="form-group">
							<!-- Added "mb-3" class for margin-bottom -->
							<label class="form-label mb-1" for="password">Password</label>
							<input
								class="form-input"
								type="password"
								id="password"
								bind:value={password}
								placeholder="Enter your password"
							/>
						</div>

						<div class="form-group">
							<button type="button" class="btn variant-filled" on:click={handleLogin}>Login</button>
						</div>

					</div>

          <div class="text-sm text-gray-500">
            <!-- Disclaimer text goes here -->
            By logging in, you agree to our terms and conditions.
            <a href="/register" class="ml-1 text-blue-500">Register</a> or
            <a href="/password" class="ml-1 text-blue-500">recover password</a>.
          </div>
			</div>
		</div>
	</div>

</main>
