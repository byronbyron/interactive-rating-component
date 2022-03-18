<script>
  let rating;
</script>

<main>
  
  <div class="card">
    <div class="icon">
      <img src="/icon-star.svg" alt="">
    </div>

    <h1>How did we do?</h1>

    <p>Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!</p>

    <div class="btn-group">
      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button>4</button>
      <button>5</button>
    </div>

    <button class="btn-primary">Submit</button>
  </div>

  <div class="card" style="display: none;">
    <p class="badge">You selected <span>out of 5</span></p>

    <h1>Thank you!</h1>

    <p>We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch!</p>
  </div>

</main>

<style>
  h1 {
    font-family: 'Overpass', sans-serif;
    font-size: 1.5rem;
    margin-top: 0;
    margin-bottom: 0.4rem;
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
    border-radius: 2.625rem;
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
    background: linear-gradient(
      to bottom,
      hsl(213, 19%, 15%),
      hsl(216, 12%, 12%)
    );
    padding: 1.5rem 1.5rem 2rem 1.5rem;
    border-radius: 1rem;
    max-width: 327px;
    margin-left: auto;
    margin-right: auto;
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

</style>
