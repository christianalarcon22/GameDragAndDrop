<script>
  import DragComponent from "./component/Drag.svelte";
  import DropComponent from "./component/Drop.svelte";

  let item = [
    { id: 1, name: "7", color:"rgb(235, 110, 128)"},
    { id: 2, name: "10", color: "rgb(247, 183, 51)"},
    { id: 3, name: "4", color: "rgb(252, 74, 26)" },
    { id: 4, name: "X", color: "darkslateblue" },
  ];

  let dropped = []; 
 

</script>

<main>
  <div class="content">
    <div class="panel-izq-flex">
      <div class="column-1">
        <div>2</div>
        <div>9</div>
        <div>2</div>
        <div>          
            <DropComponent items={dropped}  />             
        </div>
      </div>

      <div class="column-2">
        <div>+</div>
        <div>-</div>
        <div>
          <DropComponent items={dropped} />
        </div>

        <div>-</div>
      </div>

      <div class="column-3">
        <div>2</div>
        <div>
          <DropComponent items={dropped}  />
        </div>

        <div>4</div>
        <div>2</div>
      </div>

      <div class="column-4">
        <div>=</div>
        <div>=</div>
        <div>=</div>
        <div>=</div>
      </div>

      <div class="column-5">
        <div>
          <DropComponent items={dropped} />
        </div>

        <div>2</div>
        <div>8</div>
        <div>8</div>
      </div>
    </div>

    <div class="panel-der-flex">
      <div>
        <h1>ARRASTRA</h1>
      </div>
      <div>
        <DragComponent items={item}  />
      </div>
    </div>
  </div>
</main>

<style>
  /* Backgrounds */
  main {
    background-color: rgb(74, 189, 172);
  }

  .content,
  h1 {
    display: flex;
    font-family: Luckiest Guy;
    font-size: 50px;
  }

  .panel-izq-flex {
    background-color: white;
    display: grid;
    grid-template-columns: auto auto auto auto auto;
    grid-template-rows: auto auto auto auto;
    align-content: center;
    height: 420px;
    width: 60%;
    margin: 5% 0 5% 5%;
    border-radius: 5px;
    position: relative;
  }

  .panel-izq-flex > div {
    text-align: center;
    margin: 5%;
  }

  .column-1 {
    color: rgb(235, 110, 128);

  }

  .column-2,
  h1 {
    color: darkslateblue;
  }

  .column-3 {
    color: rgb(247, 183, 51);
  }

  .column-4 {
    color: rgb(252, 74, 26);
  }

  .column-5 {
    color: rgb(74, 189, 172);
  }

  /* ////////////////////////////////////////////// */
  .panel-der-flex {
    margin: 5%;
    position: relative;
  }

  
</style>
