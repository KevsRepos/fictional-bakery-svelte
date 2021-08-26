<script>
  export let alt;
  export let imgSrc;
  export let title;
  export let text;
  export let direction;
</script>
<style>
  section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }
  img {
    width: 50%;
    border: var(--mainBorder);
    box-sizing: border-box;
  }
  .textCont {
    width: 50%;
  }
  p {
    width: 30vw;
    margin: auto;
    white-space: pre-line;
  }

  @media screen and (max-width: 900px) {
    p {
      width: 97%;
    }
  }

  @media screen and (max-width: 770px) {
    section {
      flex-direction: column !important;
      position: relative;
      overflow-x: hidden;
      position: sticky;
      top: 0px;
    }
    img {
      height: 100vh;
      width: auto;
      border: none;
    }
    .textCont {
      position: absolute;
      display: inline;
      vertical-align: middle;
      width: 100vw;
    }
    h1 {
      position: sticky;
      top: 70px;
      width: 100vw;
      border-radius: none;
      margin-bottom: 80px;
    }
    h1, p {
      background-color: #ffffff;
      padding: 10px;
    }
    p {
      margin-top: 10px;
      width: 85vw;
    }
  }
</style>

<section style="flex-direction: {direction}">
  <img alt={alt} src={imgSrc} />
  <div class="textCont">
    <h1 class="heading">{title}</h1>
    <p>
      {text}
    </p>
  </div>
</section>