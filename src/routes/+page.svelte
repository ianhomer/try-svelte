<script>
  import Component from "./component.svelte";
  import Hello from "./hello.svelte";
  const foo = 1;

  let count = 0;

  $: doubled = count * 2;
  $: quadrupled = doubled * 2;
  $: if (count >= 10) {
    alert(`count is high`);
  }

  function handleClick() {
    count += 1;
  }
</script>

<h1>Try Svelte</h1>
<p>Value of foo {foo}; double foo {foo * 2}</p>
<p class="foo">Styled content</p>
<button on:click={handleClick}>
  Clicked {count} ; {doubled} : {quadrupled}
  {count === 1 ? "time" : "times"}
</button>
<Component />
<Hello />

<style>
  p.foo {
    color: purple;
  }
</style>
