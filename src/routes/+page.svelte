<script lang="ts">
    let hits: boolean[] = [false, false, false, false, false];

    function handleKeydown(e: KeyboardEvent) {
        switch(e.key){
            case ('E' || 'e'):
                hits[0] = true;
                break;
            case ('D' || 'd'):
                hits[1] = true;
                break;
            case ('A' || 'a'):
                hits[2] = true;
                break;
            case ('Q' || 'q'):
                hits[3] = true;
                break;
            case ('E' || 'e'):
                hits[4] = true;
                break;
        }
	}
</script>

<svelte:window on:keydown={handleKeydown} />

<div class="content">
    <h1>Shaiiko-Peek Helper</h1>
    <div class="keys">
        <h2>Right Peek</h2>
        <div class="peeks">
            <div class={hits[0] ? "hit" : ""}>E</div>
            <div class={hits[1] ? "hit" : ""}>D</div>
            <div class={hits[2] ? "hit" : ""}>A</div>
            <div class={hits[3] ? "hit" : ""}>Q</div>
            <div class={hits[4] ? "hit" : ""}>E</div>
        </div>
        <!-- <h2>Right Peek</h2>
        <div class="peeks">
            <div>Q</div>
            <div>A</div>
            <div>D</div>
            <div>E</div>
            <div>Q</div>
        </div> -->
    </div>
</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap');

    .content {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .keys {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .peeks {
        display: flex;
        flex-direction: row;
    }

    .peeks > div {
        display: grid;
	    align-items: center;
        text-align: center;

        width: 2em;
        height: 2em;

        margin: 0 .5em;
        padding: 0;

        background-color: rgba(0, 0, 0, 0.5);
        border-radius: .25em;
        color: white;
        font-size: 4em;
    }

    .hit {
        color: black;
        background-color: white;
    }
</style>