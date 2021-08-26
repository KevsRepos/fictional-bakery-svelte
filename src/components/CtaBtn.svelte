<script>
  export let route, value;
</script>

<style>
  a {
    padding: 10px;
    color: #ffffff;
    background-color: var(--mainColor);
    border-radius: var(--mainBorderRadius);
    font-family: var(--headingFont);
    border: var(--mainBorder);
    transition: 0.10s ease-in;
  }
  a:hover {
    text-decoration: none;
    background-color: transparent;
    color: var(--mainColor);
  }
</style>

<a href={route}>{value}</a>