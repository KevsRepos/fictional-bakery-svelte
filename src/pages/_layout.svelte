<script>
  import CtaBtn from "../components/CtaBtn.svelte";
  import Logo from "../components/Logo.svelte";

  let openMenu = false;
  let firstTouch;

  const touchStart = e => {
    firstTouch = e.touches[0].clientY;
  }

  const touchMove = e => { 
    if(firstTouch <  e.touches[0].clientY - 100) {
      openMenu = false;
    }
  }

  const links = [
    ['#UeberUns', 'Über uns'],
    ['#Sortiment', 'Sortiment'],
    ['#Jobs', 'Jobs']
  ];

</script>

<style>
  header {
    z-index: 999999;
    position: fixed;
    background-color: #ffffff;
    width: 100vw;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: var(--mainBorder);
  }
  nav {
    display: flex;
    align-items: center;
    margin-left: 50px;
  }
  nav a {
    color: var(--brandingColor);
    padding: 15px;
  }
  .ctaBtnsHeader {
    margin-right: 50px;
  }
  .betweenCta {
    margin: 0 15px;
  }

  footer {
    display: flex;
    flex-direction: column;
    justify-content: end;
    position: absolute;
    align-items: center;
    padding: 10px 0px 0px 0px;
    z-index: 9999;
    width: 100%;
  }
  footer:before {
    z-index: -1;
    content: "";
    position: absolute;
    background-image: url('/./images/footerBg.jpg');
    background-position: top;
    background-repeat: no-repeat;
    background-size: cover;
    width: 100%;
    height: 250px;
    opacity: 0.5;
    padding: 10px 0;
  }
  footer .footerLinks {
    margin-top: 30px;
    margin-bottom: 10px;
  }
  footer a {
    color: #000000;
    padding: 10px;
    text-decoration: none;
  }

  .menuBtn {
    display: none;
    border: none;
    background-color: transparent;
    fill: var(--brandingColor);
  }

  .mobile {
    display: none;
    font-family: var(--headingFont);
    color: var(--brandingColor);
    font-style: italic;
  }

  .openedMenu {
    display: flex;
    flex-direction: column;
    height: 100%;
    width: 100vw;
    background-color: #ffffff;
    position: fixed;
    bottom: 0px;
    left: 0px;
    box-shadow: var(--mainBoxShadow);
    animation-name: slideUp;
    animation-duration: 0.50s;
    margin: 0;
  }
  .openedMenu a {
    display: block;
  }
  .closedMenu {
    animation-name: slideUp;
    animation-direction: reverse;
    animation-duration: 0.50s;
  }

  @keyframes slideUp {
    from {
      height: 0vh;
    }
    to {
      height: 100%;
    }
  }


  @media screen and (max-width: 1000px) {
    .mobile, .menuBtn {
      display: initial;
    }
    header {
      padding: 20px;
    }
    nav {
      display: none;
    }
  }
  @media screen and (max-width: 550px) {
    .mobileOut {
      display: none;
    }
  }
</style>

<header>
  <button class="menuBtn" on:click={() => openMenu = !openMenu}>
    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
      <path d="M3,6H21V8H3V6M3,11H21V13H3V11M3,16H21V18H3V16Z" />
    </svg>
  </button>
  <span class="mobile" >Annies Backstübchen</span>
  <nav on:touchstart={e => touchStart(e)} on:touchmove={e => touchMove(e)} class={openMenu ? "openedMenu" : "closedMenu"}>
    <Logo />
    {#each links as [route, name]}
      <a href={route}>{name}</a>
    {/each}
  </nav>
  <div class="ctaBtnsHeader">
    <span class="mobileOut"><CtaBtn value="Bestellen" route="#Bestellen" /></span>
    <span class="mobileOut betweenCta">oder</span>
    <CtaBtn value="Anrufen" route="#Anrufen" />
  </div>
</header>
<slot />
<footer>
  <Logo />
  <div class="footerLinks">
    <a href="https://kevin-sheard.com/Impressum">Impressum</a>
    <a href="#Datenschutz">Datenschutz</a>
    <a href="#Kontakt">Kontakt</a>
  </div>
</footer>