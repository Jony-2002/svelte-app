<script>
// @ts-nocheck

  $: counter = 0;

  function handleIncrement() {
    counter++;
  }

  let stundents = [
    {
      name: "Khayom",
      age: 15,
    },
    {
      name: "Masrur",
      age: 25,
    },
    {
      name: "Khushnud",
      age: 42,
    },
  ];

  // @ts-ignore
  let userName;
  // @ts-ignore
  let userAge;

  function submitUser() {
    // console.log(userName);
    // console.log(Number(userAge));
    // @ts-ignore
    const newUser = {
      // @ts-ignore
      name: userName,
      // @ts-ignore
      age: userAge,
    };

    // @ts-ignore
    stundents = [...stundents, { name: userName, age: userAge }];
    userName = "";
    userAge = "";
  }
</script>

<div>
  <div>
    <p>
      Assignments Create a new SvelteKit project with a minimum of 2 pages and
      navigation in the +layout.svelte file. You can use the "Topics covered"
      section below as a reminder of the steps: how to create and deploy
      SvelteKit in Vercel. Also a youtube recording is available to you
      https://youtu.be/JHF8nuW1P2s Main page of your new SvelteKit project
      should be the same as your main HTML project of this course Run you
      project locally May be 'node.js' and 'npm' are not installed on your
      computer. In this case you should search on google or ask chatGPT how to
      install them on your OS. If you are not successful in installing node.js
      and npm your SvelteKit project can still be deployed and run in the Vercel
      cloud environment. Because Vercel has node.js & npm. Save the project into
      Github To complete this task, you should link VSCode and GitHub Deploy it
      in Vercel Save the link to the deployed site in the Google Form and in the
      comment add the link to the github repository of your project
    </p>
  </div>
  <div>
    <h1>{counter}</h1>
    <button on:click={handleIncrement}>Increment</button>
  </div>
  <div class="form-container">
    <input type="text" placeholder="name" bind:value={userName} />
    <input type="number" placeholder="age" bind:value={userAge} />
    <button on:click={submitUser}>Add Students</button>
  </div>
  <div>
    {#each stundents as item}
      <div>
        <h3>{item.name}</h3>
      </div>
    {/each}
  </div>
</div>

<style>
  .form-container {
    margin-top: 20px;
  }
</style>
