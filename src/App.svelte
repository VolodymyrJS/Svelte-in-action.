<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import Input from './UI/Input.svelte';

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
    margin-top: 4rem;
  }

  .learning-to-code img {
    margin-top: 15px;
    width: 60px;
    height: 60px;
    -webkit-transition: -webkit-transform .8s ease-in-out;
    transition: transform .8s ease-in-out;
    border-bottom: 5px solid lightskyblue;
    box-shadow: 0 8px 6px -6px black;
  }

  .learning-to-code img:hover {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }


  .col-xs-12 {
    padding: 0;
    margin: 0;
  }

  .row {
    margin: 0;
  }

  .add-meetup-btn {
    width: 100%;
  }

  .form {
    margin-top: 15px;
  }

</style>

<Header />

<main>
  <div class="row">
    <div class="col-xs-1 col-xs-offset-1 learning-to-code">
      <img src="images/c++.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/cs.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/css.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/html.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/java.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/js.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/php.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/python.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/ruby.png" alt="add-meetup">
    </div>
    <div class="col-xs-1 learning-to-code">
      <img src="images/stack-overflow.png" alt="add-meetup">
    </div>
  </div>
  <div class="row">
    <div class="col-xs-12">
      <form class="form" on:submit|preventDefault={addMeetup}>
        <div class="row">
          <div class="col-xs-4 col-xs-offset-2">
            <Input 
              id="title"
              label="Title"
              type="text"
              value={title}
            on:input={event => (title = event.target.value)} />
            <Input
              id="subtitle"
              label="Subtitle"
              type="text"
              value={subtitle}
              on:input={event => (subtitle = event.target.value)} />
            <Input
              id="address"
              label="Address"
              type="text"
              value={address}
              on:input={event => (address = event.target.value)} />
          </div>
          <div class="col-xs-4">
            <Input
              id="imageUrl"
              label="Image URL"
              type="text"
              value={imageUrl}
            on:input={event => (imageUrl = event.target.value)} />
            <Input
              id="email"
              label="E-Mail"
              type="email"
              value={email}
              on:input={event => (email = event.target.value)} />
            <Input
              id="description"
              label="Description"
              controlType="textarea"
              value={description}
              on:input={event => (description = event.target.value)} />
          </div>
        </div>
        <div class="row">
          <div class="col-xs-2 col-xs-offset-5">
            <button class="add-meetup-btn" type="submit">Add meetup</button>
          </div>
        </div>
      </form>
    </div>
  </div>
  <MeetupGrid {meetups} />
</main>