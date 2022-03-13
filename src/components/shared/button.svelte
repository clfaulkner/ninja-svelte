<script>
    export let type = 'primary'
    export let flat = false
    export let inverse = false
</script>

<button class={type} class:flat={flat} class:inverse={inverse}>
    <slot></slot>
</button>

<style>
    button{
        border: 0px;
        cursor: pointer;
        border-radius: 6px;
        padding: 8px 12px;
        font-weight: bold;
        box-shadow: 1px 2px 3px lightgray;
    }
    .primary{
        background-color: red;
        color: whitesmoke
    }
    .secondary{
        background-color:forestgreen;
        color: whitesmoke 
    }
    .flat{
        box-shadow: none;
    }
    .primary.inverse{
        background-color: whitesmoke;
        color: red;
        border-color: red;
    }
    .secondary.inverse{
        background-color:whitesmoke;
        color: forestgreen;
        border: 2px solid;
        border-color: forestgreen;
    }
</style>