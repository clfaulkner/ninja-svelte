<script>
    import Header from "./components/Header.svelte"
    import Footer from "./components/Footer.svelte"
    import Tabs from './components/shared/Tabs.svelte'
    import Pollform from './components/Pollform.svelte'

    let items = ['Current Polls', 'Add New Poll']
    let activeItem = 'Current Polls'

    const tabChange = (e)=>{activeItem=e.detail}
</script>

<Header />
<main>
    <Tabs {activeItem} {items} on:tabChange={tabChange}/>
    {#if activeItem==='Current Polls'}
        <p>Current Polls component goes here</p>
    {:else if activeItem==='Add New Poll'}
        <Pollform />
    {/if}
</main>
<Footer />

<style>
    main{
        max-width: 960px;
        margin: 40px auto;
    }
</style>