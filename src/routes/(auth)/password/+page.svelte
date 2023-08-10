<script>
  let email = '';

  function handlePasswordRecovery() {
    // Handle password recovery logic here
  }
</script>

<main class="flex justify-center items-center h-screen">
  <div class="container mx-auto flex justify-center items-center">
    <div class="columns">
      <div class="column col-12 col-md-8 col-mx-auto my-5">
        <div class="card p-3 mx-auto min-h-[480px] min-w-[640px] flex flex-col justify-center items-center space-y-8">
          <div class="card-header mb-4">
            <h4 class="card-title">Recover Password</h4>
          </div>

          <div class="card-body flex flex-col space-y-8">
            <div class="form-group">
              <label class="form-label" for="email">Email</label>
              <input
                class="form-input"
                type="email"
                id="email"
                bind:value={email}
                placeholder="Enter your email"
              />
            </div>

            <div class="form-group">
              <button type="button" class="btn variant-filled" on:click={handlePasswordRecovery}>Recover Password</button>
            </div>
          </div>

          <div class="text-sm text-gray-500">
            An email will be sent to the provided address with instructions to reset your password.
            <a href="/login" class="ml-1 text-blue-500">Login</a> or
            <a href="/register" class="ml-1 text-blue-500">register</a>.
          </div>
        </div>
      </div>
    </div>
  </div>
</main>
