<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";

  let meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code in 2 hours",
      description:
        "In this meetup, we will have some experts that teach you how to code!",
      imageUrl:
        "https://blog.vilmatech.com/wp-content/uploads/2019/05/svelte.jpg",
      address: "27th Nerd Road, 32523 New York",
      contactEmail: "code@test.com"
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Let's go for some swimming",
      description: "We will simply swim some rounds!",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Olympic_swimming_pool_%28Tbilisi%29.jpg/800px-Olympic_swimming_pool_%28Tbilisi%29.jpg",
      address: "27th Nerd Road, 32523 New York",
      contactEmail: "swim@test.com"
    }
  ];

  let title = '';
  let subtitle = '';
  let description = '';
  let imageUrl = '';
  let address = '';
  let email = '';

  function addMeetup() {
    console.log('addMeetup was clicked');
    const newMeetup = {
        id: Math.random(),
        title: title,
        subtitle: subtitle,
        description: description,
        imageUrl: imageUrl,
        address: address,
        contactEmail: email
    };
    meetups = [...meetups, newMeetup];
  }

</script>

<style>
  main {
    margin-top: 5rem;
  }
</style>

<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
    <div class="form-group">
        <label for="title">Title</label>
        <input type="text" bind:value={title} />
    </div>
    <div class="form-group">
        <label for="title">Subtitle</label>
        <input type="text" bind:value={subtitle} />
    </div>
    <div class="form-group">
        <label for="title">Description</label>
        <textarea type="text" bind:value={description}></textarea>
    </div>
    <div class="form-group">
        <label for="title">ImageUrl</label>
        <input type="text" bind:value={imageUrl} />
    </div>
    <div class="form-group">
        <label for="title">Address</label>
        <input type="text" bind:value={address} />
    </div>
    <div class="form-group">
        <label for="title">Email</label>
        <input type="email" bind:value={email} />
    </div>
    <button type="submit">Add meetup</button>
  </form>
  <MeetupGrid {meetups} />
</main>