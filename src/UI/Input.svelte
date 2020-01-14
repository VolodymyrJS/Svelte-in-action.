<script>

    export let controlType = null;
    export let type = "text";
    export let id;
    export let label;
    export let value;
    export let rows = null;

</script>

<style>
  input,
  textarea {
    display: block;
    width: 100%;
    font: inherit;
    border: none;
    border: 2px solid transparent;
    border-bottom: 4px solid transparent;
    border-radius: 3px 3px 0 0;
    background: white;
    padding: 0.15rem 0.25rem;
    transition: border-color 0.1s ease-out;
    padding: 10px 15px;
    box-shadow: 0 8px 6px -6px #555;
    border-radius: 4px;
    color: lightslategrey;
    font-weight: 600;
    font-style: italic;
  }

  input:focus,
  textarea:focus {
    border-color: lightskyblue;
    outline: none;
    box-shadow: 0 0 5px rgba(81, 203, 238, 1);
    border: 2px solid rgba(81, 203, 238, 1);
    border-bottom: 4px solid rgba(81, 203, 238, 1);
    box-shadow: 0 8px 6px -6px black;
  }

input:-webkit-autofill,
input:-webkit-autofill:hover, 
input:-webkit-autofill:focus,
textarea:-webkit-autofill,
textarea:-webkit-autofill:hover,
textarea:-webkit-autofill:focus {
  -webkit-text-fill-color: lightslategrey;
}

  label {
    display: block;
    margin-bottom: 0.5rem;
    width: 100%;
    color: rgba(81, 203, 238, 1);
    font-weight: 600;
  }

  .form-control {
    padding: 0.5rem 0;
    width: 100%;
    margin: 0.25rem 0;
  }

  .form-control label {
    padding-left: 1rem;
  } 

</style>

<div class="form-control">
    <label for={id}>{label}</label>
    {#if controlType === 'textarea'}
        <input {id} {rows} {value} on:input />
    {:else}
        <input type={type} {id} {value} on:input />
    {/if}
</div>