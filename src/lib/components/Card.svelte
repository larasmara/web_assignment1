<script>
    export let value;
    export let suit;
    export let color;
    export let flipped = true;
</script>

<button
    class="card"
    class:flipped={flipped}
    on:click={() => flipped = !flipped}
>
    <div class="card-front text-xl text-black bg-rose-300 ">
        <div>
            {value} of {suit} ({color} card)
        </div>
    </div>

    <div class="card-back"> </div>
</button>

<style>
    .card {
        position: relative;
		aspect-ratio: 2.5 / 3.5;
		font-size: 0.25em;
		height: 70em;
		border-radius: 2em;
		transform: rotateY(180deg);
		transition: transform 0.3s;
		transform-style: preserve-3d;
		padding: 0;
        margin: 8px;
		user-select: none;
		cursor: pointer;

    }
    .card-front, .card-back {
		position: absolute;
		width: 100%;
		height: 100%;
		left: 0;
		top: 0;
		backface-visibility: hidden;
		border-radius: 20px;
		border: 1px solid var(--fg-2);
		box-sizing: border-box;
		padding: 2em
    }

    .card-back {
        background: url(./images/card_back.png) no-repeat;
        background-size: 100%;
        transform: rotateY(180deg);
    }

    /* whenver flipped is true, the transform becomes rotateY(0) instead of rotateY(180) */
    .card.flipped { 
        transform: rotateY(0);
    }

</style>