<script>
  import { fade } from 'svelte/transition';
  let form = { submitted: false };
  let rating;

  function updateRating() {
    rating = parseInt(this.textContent);
  }

  function handleSubmit() {
    if (!rating) return;
    form.submitted = true;
  }
</script>

<main>
  {#if !form.submitted}
    <div class="card">
      <div class="icon">
        <svg width="17" height="16" xmlns="http://www.w3.org/2000/svg"><path d="m9.067.43 1.99 4.031c.112.228.33.386.58.422l4.45.647a.772.772 0 0 1 .427 1.316l-3.22 3.138a.773.773 0 0 0-.222.683l.76 4.431a.772.772 0 0 1-1.12.813l-3.98-2.092a.773.773 0 0 0-.718 0l-3.98 2.092a.772.772 0 0 1-1.119-.813l.76-4.431a.77.77 0 0 0-.222-.683L.233 6.846A.772.772 0 0 1 .661 5.53l4.449-.647a.772.772 0 0 0 .58-.422L7.68.43a.774.774 0 0 1 1.387 0Z" fill="#FC7614"/></svg>
      </div>

      <h1>How did we do?</h1>

      <p>Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>

      <form on:submit|preventDefault={handleSubmit}>
        <div class="btn-group">
          <button type="button" on:click={updateRating} class:selected={rating === 1}>1</button>
          <button type="button" on:click={updateRating} class:selected={rating === 2}>2</button>
          <button type="button" on:click={updateRating} class:selected={rating === 3}>3</button>
          <button type="button" on:click={updateRating} class:selected={rating === 4}>4</button>
          <button type="button" on:click={updateRating} class:selected={rating === 5}>5</button>
        </div>

        <button type="submit" class="btn-primary">Submit</button>
      </form>
    </div>
  {:else}
    <div class="card text-center" transition:fade>
      <img src="/illustration-thank-you.svg" alt="" width="162" height="108" class="illustration">

      <p class="badge">You selected {rating} out of 5</p>

      <h1>Thank you!</h1>

      <p class="mb-0">We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch!</p>
    </div>
  {/if}
</main>

<style>
  h1 {
    font-family: 'Overpass', sans-serif;
    font-size: 1.5rem;
    margin-top: 0;
    margin-bottom: 0.5rem;
    color: var(--white);
  }

  p {
    font-size: 15px;
    line-height: 1.45;
    margin-top: 0;
    margin-bottom: 1.75rem;
    color: var(--medium-grey);
    letter-spacing: -0.05rem;
  }

  img {
    width: 0.875rem;
  }

  button {
    font-size: 13px;
    line-height: 2.875rem;
    display: flex;
    justify-content: center;
    width: 2.625rem;
    height: 2.625rem;
    border: 0;
    border-radius: 4rem;
    color: var(--medium-grey);
    background-color: var(--dark-blue);
    cursor: pointer;
    transition: color 0.15s, background-color 0.15s;
  }

  button:hover,
  button:focus {
    color: var(--white);
    background-color: var(--orange);
  }

  main {
    width: 100%;
    padding-left: 1.5rem;
    padding-right: 1.5rem;
  }

  .card {
    background: radial-gradient(
      circle at top,
      hsl(215, 20%, 17%),
      hsl(216, 18%, 12%)
    );
    padding: 1.5rem 1.5rem 2rem 1.5rem;
    border-radius: 1rem;
    max-width: 327px;
    margin: 3px auto 0;
    min-height: 360px;
  }

  .icon {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 2.5rem;
    height: 2.5rem;
    background-color: var(--dark-blue);
    border-radius: 2.5rem;
    margin-bottom: 1rem;
  }

  .btn-group {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1.5rem;
  }

  .btn-primary {
    font-size: 14px;
    line-height: 50px;
    width: 100%;
    padding: 0 1rem;
    height: 45px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--white);
    background-color: var(--orange);
    transition: color 0.15s, background-color 0.15s;
  }

  .btn-primary:hover,
  .btn-primary:focus {
    color: var(--orange);
    background-color: var(--white);
  }

  .illustration {
    display: block;
    width: 145px;
    height: auto;
    margin: 0.625rem auto 1.5rem;
  }

  .badge {
    line-height: 1;
    display: inline-block;
    color: var(--orange);
    background-color: var(--dark-blue);
    margin-bottom: 1.375rem;
    padding: 10px 0.875rem 7px;
    border-radius: 2rem;
    letter-spacing: 0.01em;
  }

  .selected {
    color: var(--white);
    background-color: var(--medium-grey);
  }

  .text-center {
    text-align: center;
  }

  .mb-0 {
    margin-bottom: 0;
  }

  @media (min-width: 992px) {
    h1 {
      font-size: 1.75rem;
      margin-bottom: 0.25rem;
    }

    p {
      font-size: 1rem;
      line-height: 1.5;
    }

    button {
      font-size: 1rem;
      line-height: 3.25rem;
      width: 3.125rem;
      height: 3.125rem;
    }

    .card {
      max-width: 410px;
      min-height: 415px;
      border-radius: 2rem;
      padding: 2rem 2.5rem 2rem 2rem;
    }

    .icon {
      width: 3rem;
      height: 3rem;
      border-radius: 3rem;
      margin-bottom: 1.75rem;
    }

    .btn-group {
      margin-bottom: 2rem;
    }

    .btn-primary {
      font-size: 1rem;
    }

    .illustration {
      width: 162px;
      margin: 0.875rem auto 2rem;
    }

    .badge {
      font-size: 0.875rem;
      margin-bottom: 2rem;
      padding: 10px 1.25rem 7px;
      letter-spacing: 0.01em;
    }
  }
</style>
