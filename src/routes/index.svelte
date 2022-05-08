
<script>
    import star from "/static/icon-star.svg"
    import thankyou from "/static/illustration-thank-you.svg"
    let rating = ""
    let submit = false
    let norating = false



    let screen = true

function checkRating(){

    if(rating === "")
    
    {   norating = true

    }else{ 
        screen = false
     console.log(screen)
}}


</script>


<div class="container gradient">

    {#if screen }

	<div class="star">
        <img src="icon-star.svg" alt="star">
    </div>
	<div>
		<h1>How did we do?</h1>
		<p>
			Please let us know how we did with your support request. All feedback is appreciated to help
			us improve our offering!
		</p>
	</div>
	<div class="rating">
        <div class="{rating === '1' ? 'selected' : 'notselected'}"
        on:click="{() => {rating = '1'; norating = false}}" >1</div>
        <div class="{rating === '2' ? 'selected' : 'notselected'}"
        on:click="{() => {rating = '2'; norating = false}}" >2</div>
        <div class="{rating === '3' ? 'selected' : 'notselected'}"
        on:click="{() => {rating = '3'; norating = false}}" >3</div>
        <div class="{rating === '4' ? 'selected' : 'notselected'}"
        on:click="{() => {rating = '4'; norating = false}}" >4</div>
        <div class="{rating === '5' ? 'selected' : 'notselected'}"
        on:click="{() => {rating = '5'; norating = false}}" >5</div>
        
    </div>
  

    {#if norating }


    <div class="warning"> Please choose a rating before submit. Thank you!</div>
        
    {/if}

	<div on:click="{checkRating}" class="btn">
        <p >SUBMIT</p>
    </div>

{:else}
    <div class="thankyou">
        <div>
            <img src="illustration-thank-you.svg" alt="machine">
        </div>
        <div>
            <p class="p-thankyou"> You've selected {rating} out of 5 <p>
        </div>
        <div>
            <h1> Thank You!</h1>
        </div>
        <div>
            <p> We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch! </p>
        </div>
    </div>


{/if}

</div>

<style>
	.container {
		background-color: hsl(216, 12%, 54%);
		max-width: 375px;
		margin: 0 auto;
		padding: 30px;
		border-radius: 15px;
		color: white;
		font-family: overpass;
	}

	h1 {
		font-size: 30px;
		font-weight: 700;
	}

    p {
        font-size: 15px;
        font-weight: 100;
    }

    .gradient {
        background-image: linear-gradient(
  180deg,
  hsl(216deg 12% 54%) 0%,
  hsl(216deg 11% 51%) 19%,
  hsl(216deg 12% 47%) 27%,
  hsl(216deg 13% 44%) 34%,
  hsl(215deg 13% 40%) 41%,
  hsl(215deg 14% 37%) 47%,
  hsl(215deg 15% 34%) 53%,
  hsl(214deg 16% 31%) 59%,
  hsl(214deg 17% 27%) 66%,
  hsl(214deg 18% 24%) 73%,
  hsl(214deg 19% 21%) 81%,
  hsl(213deg 20% 18%) 100%
);
    }

    .star {
        display: flex;
        justify-content: center;
        align-items: center;
        max-width: fit-content;
        background-color: hsl(216, 12%, 54%);
        padding: 10px;
        border-radius: 100%;
    }

    .rating {
        margin-top: 30px;
        display: flex;
        justify-content: space-between;
    }

    .rating div{
        width: 30px;
        height: 30px;
        padding: 7.5px;
        border-radius: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .rating div:hover {

        background-color: hsl(216, 12%, 54%);

    }

    .notselected {

        background-color: hsl(213, 19%, 18%);
    }

    .selected {

        background-color: hsl(25, 97%, 53%);

    }

    .btn {
        width: auto;
        background-color: hsl(25, 97%, 53%);
        border-radius: 30px;
        height: 45px;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 30px;
    }

    .btn:hover {
        background-color:white;
        color: hsl(25, 97%, 53%);
    }

    .warning {
        margin-top: 30px;
        color: hsl(25, 97%, 53%);
        font-size: 10px;
    }

    .thankyou {
        margin: 30px 0px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        row-gap: 15px;
        text-align: center;
        line-height: 150%;
        font-weight: 400;
    }

    .p-thankyou {
       background-color: hsl(213, 19%, 18%);
       padding: 10px 30px;
       border-radius: 30px;
       font-size: 15px;
       color: hsl(25, 97%, 53%);;
    }

</style>
