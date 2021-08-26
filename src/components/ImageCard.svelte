<script>
  export let imgPath, imgAlt, text;
</script>

<style>
  .imgCard {
    border-radius: var(--mainBorderRadius);
    box-shadow: var(--mainBoxShadow);
    border: var(--mainBorder);
    position: relative;
    width: min-content;
    padding-bottom: 15px;
    background-color: #ffffff;
    margin: 30px;
    z-index: 99999;
  }
  img {
    width: 250px;
    border-top-left-radius: var(--mainBorderRadius);
    border-top-right-radius: var(--mainBorderRadius);
  }
  .text {
    padding: 20px;
  }
</style>

<div class="imgCard">
  <img alt={imgAlt} src={imgPath} />
    <div class="text">
      {text}
    </div>
</div>
