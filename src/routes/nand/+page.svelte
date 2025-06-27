<h1>Nand</h1>

<style>
    .slider {
        position: absolute;  
        background-color: #ccc;
        transition: .4s;
        cursor: pointer;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        border-radius: 5px;
    }

    .switch{
        display: inline-block;
        position: relative;
        height: 27px ;
        width:52px;
    }

    .switch input {
       display: none; 
    }


    input:checked + .slider {
        background-color: blue;
    }

    input:checked + .slider:before {
        transform: translateX(26px);
    }

    .slider:before {
        position: absolute;
        content: "";
        height:19px;
        width: 19px;
        background-color: white;
        left: 4px;
        bottom: 4px;
        transition: 0.4s;
        border-radius: 10px;
    }

    
</style>

<script>

let eingabe1 = false
let eingabe2 = false
let ausgabe = true

function check() { 
    console.log(eingabe1,eingabe2,ausgabe)
    if (!(eingabe1 && eingabe2)){
        ausgabe = true
    }

    else (
        ausgabe = false
    )


    
}

$: console.log(eingabe1,eingabe2,ausgabe)


</script>



<p>Toggle 1</p>
<label class="switch">
    <input type="checkbox" bind:checked={eingabe1} on:change={check}>
  <span class="slider"></span>
</label>

<br>


<p>Toggle 2</p>
<label class="switch">
    <input type="checkbox" bind:checked={eingabe2} on:change={check}>
  <span class="slider"></span>
</label>

<br>
<br>
<hr style="height:0,001px;">
<br>


<p>Ausgabe</p>
<label class="switch">
    <input disabled type="checkbox" bind:checked={ausgabe}>
  <span class="slider"></span>
</label>



