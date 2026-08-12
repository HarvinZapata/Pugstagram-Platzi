<script>
    import { onMount } from 'svelte';
    import Header from '../components/Header.svelte';
    import Main from '../components/Main.svelte';
    import Sidebar from '../components/Sidebar';
    import TimeLine from '../components/TimeLine.svelte'
    import fallback from '../data.js';

    let data = {};
    const API = 'https://us-central1-pubstagram-co.cloudfunctions.net/data';
    onMount(async () => {
        try {
            const response = await fetch(API);
            if (!response.ok) throw new Error('API response not ok');
            data = await response.json();
        } catch (err) {
            data = fallback;
        }
    });

</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Arvo:ital,wght@0,400;0,700;1,400;1,700&family=Cinzel+Decorative:wght@400;700;900&family=Cinzel:wght@400..900&family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');
    :global(body) {
        background-color: #fafafa;
        color: rgba(38, 38, 38, 0.7);
        font-family: "Lato", sans-serif;
        margin: 0;
        padding: 0;
    }
    :global(h1, h2, h3) {
        margin: 0;
        padding: 0;
    }
</style>

<Header>

</Header>

<Main>
    <TimeLine  posts={data.posts}/>
    <Sidebar {...data.user} />
</Main>