<script>
    export let color;
</script>

<section class="card" style={`--color: ${color}`}>
    <slot name="icon"></slot>
    <slot name="header"></slot>
    <slot name="content"></slot>
    <slot name="callAction"></slot>
</section>

<style>
    .card {
        --color : 0;
        background: var(--color);
        display: grid;
        grid-template: 1fr 1fr 2fr 2fr / 1fr;
        box-sizing: border-box;
        padding: 50px;

        width: 20vw;
        height: 60vh;
    }

    @media screen and (max-width: 375px) {
  		.card {
            row-gap: 20px;
            padding: 40px;
            width: 80vw;
            height: 25vh;
        } 
	}
</style>