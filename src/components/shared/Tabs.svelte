<script>
    import {createEventDispatcher} from 'svelte'
    const dispatch = createEventDispatcher()

    export let items
    export let activeItem
</script>

<div class="tabs">
    <ul>
        {#each items as item}
        <li on:click={()=>dispatch('tabChange', item)}>
            <!--?? why not just use ID vc. class -->
            <div class:active={item=== activeItem}>{item}</div> 
        </li>
        {/each}

    </ul>
</div>

<style>
    .tabs {
        margin-bottom: 40px;
    }
    ul {
        display: flex;
        justify-content: center;
        padding: 0px;
        list-style-type: none;
    }
    li {
        margin: 0px 16px;
        font-size: 18px;
        color: rgb(219, 217, 217);
        cursor: pointer;
    }
    .active {
        color:crimson;
        border-bottom: 2px solid crimson;
        padding-bottom: 8px;
    }
</style>