<script>
  import { onMount } from "svelte";
  import BigButton from "../components/BigButton.svelte";
  import FuncButton from "../components/FunctionalButton.svelte";
  import MiddleKey from "../components/MiddleButton.svelte";
  import YellowButton from "../components/YellowButton.svelte";

  export let turnOn;
  export let turnOff;
  export let updateDisplay;
  export let handleNumberInsert;
  export let handleFunction;
  export let status;
  export let easterEgg;

  // onMount(() => {
  //   const elements = document.querySelectorAll("button");
  //   elements.forEach(el => el.addEventListener("click", hi));
  //   // console.log(elements);
  // });
</script>

<style>
  .keyboard-container {
    position: absolute;
    margin-top: 10px;
    box-sizing: border-box;
    width: 100vw;
    height: 63vh;
    padding: 10vh 20vw 5vh;

    background-color: #c9cfcb;
  }

  .keyboard-container::after {
    content: "";
    width: 45vw;
    height: 1vh;
    position: absolute;

    background-color: #c9cfcb;
    border: 5px #7b7d7c solid;
    border-top-color: transparent;
    border-bottom-color: transparent;
    top: 0;
    margin-left: 7vw;
    transform: translateY(-1.5vh);
  }

  .keyboard-container::before {
    content: "Pense Bem®";

    position: absolute;
    display: inline-block;
    width: 20vw;
    height: 5vh;
    margin-right: 20vw;
    border-radius: 10px;
    right: 0;
    top: 0;

    background-color: #ceceac;
    margin-left: 5vw;
    margin-top: 3vh;

    border: 2px #91907c solid;

    color: #3867c1;
    font-size: 5vh;
    font-weight: bold;

    text-align: center;

    /* transform: translateY(-1.5vh); */
  }

  .keyboard-container .inner-keyboard-container {
    box-sizing: border-box;
    height: 100%;
    width: 100%;
    background-color: #7b7d7c;
    padding: 1vw;
    border-radius: 1vh;
    border: 2px #625f56 solid;

    display: flex;
    flex-direction: row;
    justify-content: space-between;

    flex-wrap: wrap;
  }

  .keyboard-container .inner-keyboard-container .big-buttons-list {
    display: flex;
    flex-direction: row;
    min-width: 50%;
    max-width: 50%;
    min-height: 20vh;
    max-height: 20vh;
  }

  .keyboard-container .inner-keyboard-container .wrap-functions {
    display: inline-block;
    min-width: 50%;
    max-width: 50%;
    min-height: 20vh;
    max-height: 20vh;
  }

  .keyboard-container .inner-keyboard-container .big-buttons-list li {
    margin-left: 1vw;
  }

  .keyboard-container .inner-keyboard-container .wrap-functions .func-butons {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
  }

  .keyboard-container
    .inner-keyboard-container
    .wrap-functions
    .func-butons
    li {
    margin-right: 1vw;
  }

  .keyboard-container .inner-keyboard-container .wrap-functions .oper-buttons {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    margin-right: 2vw;
  }

  .keyboard-container
    .inner-keyboard-container
    .wrap-functions
    .oper-buttons
    li {
    margin-right: 1vw;
  }

  .keyboard-container .inner-keyboard-container .wrap-middle {
    display: flex;
    align-items: center;
    justify-content: center;

    height: 2vh;
    min-width: 100%;
    max-width: 100%;
    min-height: 10vh;
    max-height: 10vh;
  }

  .keyboard-container .inner-keyboard-container .wrap-middle .middle-buttons {
    display: flex;
    margin-left: 1vw;
  }

  .keyboard-container
    .inner-keyboard-container
    .wrap-middle
    .middle-buttons
    li {
    margin-left: 1.5vw;
  }

  .keyboard-container .inner-keyboard-container .wrap-yellow {
    display: flex;
    align-items: center;
    justify-content: center;

    height: 2vh;
    min-width: 100%;
    max-width: 100%;
    min-height: 10vh;
    max-height: 10vh;
  }

  .keyboard-container .inner-keyboard-container .wrap-yellow .yellow-buttons {
    display: flex;
    margin-right: 2vw;
  }

  .keyboard-container
    .inner-keyboard-container
    .wrap-yellow
    .yellow-buttons
    li {
    margin-right: 1.5vw;
  }
</style>

<section class="keyboard-container">
  <div class="inner-keyboard-container">
    <ul class="big-buttons-list">
      <li>
        <BigButton key="A" color="red" {status} action={easterEgg} />
      </li>
      <li>
        <BigButton key="B" color="yellow" {status} action={easterEgg} />
      </li>
      <li>
        <BigButton key="C" color="blue" {status} action={easterEgg} />
      </li>
      <li>
        <BigButton key="D" color="green" {status} action={easterEgg} />
      </li>

    </ul>
    <section class="wrap-functions">
      <ul class="func-butons">
        <li>
          <FuncButton
            text="enter"
            color="white"
            fontColor="blue"
            {status}
            action={handleFunction} />
        </li>
        <li>
          <FuncButton
            text="livro"
            color="white"
            fontColor="blue"
            {status}
            action={handleFunction} />
        </li>
        <li>
          <FuncButton
            text="desl."
            color="red"
            fontColor="blue"
            action={turnOff}
            {status} />
        </li>
        <li>
          <FuncButton
            text="liga"
            color="green"
            fontColor="blue"
            action={turnOn}
            {status} />
        </li>
      </ul>
      <ul class="oper-buttons">
        <li>
          <FuncButton
            text="+"
            color="blue"
            fontColor="white"
            {status}
            action={handleFunction} />
        </li>
        <li>
          <FuncButton
            text="-"
            color="blue"
            fontColor="white"
            {status}
            action={handleFunction} />
        </li>
        <li>
          <FuncButton
            text="X"
            color="blue"
            fontColor="white"
            {status}
            action={handleFunction} />
        </li>
        <li>
          <FuncButton
            text="÷"
            color="blue"
            fontColor="white"
            {status}
            action={handleFunction} />
        </li>
      </ul>
    </section>
    <section class="wrap-middle">
      <ul class="middle-buttons">
        <li>
          <MiddleKey
            number="0"
            text="pausa"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="1"
            text="dó"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="2"
            text="ré"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="3"
            text="mi"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="4"
            text="fá"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="5"
            text="sol"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="6"
            text="lá"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="7"
            text="si"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="8"
            text="dó"
            action={handleNumberInsert}
            {status} />
        </li>
        <li>
          <MiddleKey
            number="9"
            text="ré"
            action={handleNumberInsert}
            {status} />
        </li>
      </ul>
    </section>
    <section class="wrap-yellow">
      <ul class="yellow-buttons">
        <li>
          <YellowButton text="adição" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="subtração" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="multiplicação" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="divisão" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="aritmética" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="operação" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="siga-me" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton text="memória tons" {status} action={handleFunction} />
        </li>
        <li>
          <YellowButton
            text="número do meio"
            {status}
            action={handleFunction} />
        </li>
        <li>
          <YellowButton
            text="advinhe o número"
            {status}
            action={handleFunction} />
        </li>
      </ul>
    </section>
  </div>
</section>
