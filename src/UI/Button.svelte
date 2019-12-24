<script>
    export let capture;
    export let type;
    export let href;
    export let mode;
</script>

<style>

    button {
        width: 100%;
        padding-top: 15px;
        padding-bottom: 15px;
        text-align: center;
        color: #000;
        text-transform: uppercase;
        font-weight: 600;
        margin-left: 30px;
        margin-top: 20px;
        margin-bottom: 30px;
        cursor: pointer;
        display: inline-block;
        border-radius: 4px;
        background-color: rgba(81, 203, 238, 1);
        border: 3px solid rgba(81, 203, 238, 1);
        color: #ff0251;
        transition: .3s;
        box-shadow:
        0 1px rgba(255,255,255,.2) inset,
        0 3px 5px rgba(0,1,6,.5),
        0 0 1px 1px rgba(0,1,6,.2);
        transition: .2s ease-in-out;
    }

    button:hover {
        animation: pulse 1s infinite;
        transition: .3s;
    }
    @keyframes pulse {
        0% {
            transform: scale(1);
        }
        70% {
            transform: scale(.9);
        }
        100% {
            transform: scale(1);
        }
    }

        a {
        width: 100%;
        padding-top: 15px;
        padding-bottom: 15px;
        text-align: center;
        color: #000;
        text-transform: uppercase;
        font-weight: 600;
        margin-left: 30px;
        margin-top: 20px;
        margin-bottom: 30px;
        cursor: pointer;
        display: inline-block;
        border-radius: 4px;
        background-color: rgba(81, 203, 238, 1);
        border: 3px solid rgba(81, 203, 238, 1);
        color: #ff0251;
        transition: .3s;
        box-shadow:
        0 1px rgba(255,255,255,.2) inset,
        0 3px 5px rgba(0,1,6,.5),
        0 0 1px 1px rgba(0,1,6,.2);
        transition: .2s ease-in-out;
    }

    a:hover {
        animation: pulse 1s infinite;
        transition: .3s;
    }
    @keyframes pulse {
        0% {
            transform: scale(1);
        }
        70% {
            transform: scale(.9);
        }
        100% {
            transform: scale(1);
        }
    }

    .meetup-item {
        margin: 0;
        background-color: transparent;
        font-size: 13px;
    }

    .meetup-mail-item {
        margin: 0;
        background-color: transparent;
        text-decoration: none;
        font-size: 13px;
    }

</style>

{#if href}
<a class={mode} {href}>{capture}</a>
{:else}
<button class={mode} type="{type}">{capture}</button>
{/if}