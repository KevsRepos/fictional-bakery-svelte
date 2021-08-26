<script>
  import CtaBtn from "../components/CtaBtn.svelte";
  import ImageCard from "../components/ImageCard.svelte";
import Formular from "../components/index/Formular.svelte";
  import ImageSection from "../components/index/ImageSection.svelte";

  const imageSectionValues = [
    {
      alt: "Annie unsere Meisterbäckerin",
      imgSrc: '/./images/annie.jpg',
      title: 'Unsere Meisterbäckerin',
      text: "Ich habe die Bäckerei 2014 von meinem Vater übernommen und führe somit die lange Tradition meiner Familie fort. Seit 1958 und in der 3. Generation backen wir nämlich schon hier in Dunkelheim für unsere über die Generationen hinweg begleitenden Kunden. Unser Familienbetrieb wird auch in Zukunft für Sie die besten Backwaren in Deutschland täglich frisch zubereiten!",
      direction: 'row'
    },
    {
      alt: "Das ist unsere App",
      imgSrc: '/./images/app.jpg',
      title: 'einfach online bestellen!',
      text: "Seit neuestem bieten wir nun auch die Möglichkeit online per KnopfdruckIhre Brötchen zu sich nach Hause bestellen zu lassen! Sie können regelmäßige Bestellungen aufgeben, Ihre Bestellungen je nach Wochentag anpassen, Uhrzeiten auswählen und einiges mehr! Extra für Sie entwickelt!",
      direction: 'row-reverse'
    },
    {
      alt: "Das ist unsere Bäckerei",
      imgSrc: '/./images/bakery.jpg',
      title: 'Oder persönlich vorbei kommen',
      text: `Mo - Fr: 04:30 Uhr bis 16:30 Uhr
      Sa - So + Feieratage: 04:30 - 11:00
      Am 1. Weihnachtstag und Karfreitag haben wir geschlossen
      Frühstück gibt es bis 10:00 Uhr`,
      direction: 'row'
    }
  ];

  const imgCardValues = [
    {
      imgPath: '/./images/coffee.jpg',
      imgAlt: 'Genießen sie heißen Kaffee bei uns',
      text: 'Wir servieren jeden morgen Kaffee und Kuchen. Genießen Sie Ihr Frühstück mit der aktuellen Zeitung in einem schönem Ambiente'
    },
    {
      imgPath: '/./images/bakeryInside.jpg',
      imgAlt: 'Das ist unsere Bäckerei',
      text: 'Erlesene Backwaren, Handgemacht und mit traditionellem Rezept, jeden morgen frisch für Sie zubereitet.'
    },
    {
      imgPath: '/./images/pastries.jpg',
      imgAlt: 'Eine Auswahl unseres Gebäcks',
      text: 'Nicht nur Brötchen, sondern auch Gebäck haben wir im Angebot. Auf Nachfrage auch Ihr Wunschgebäck.'
    }
  ];
</script>

<style>
  .landingBanner {
    position: relative;
    top: 0px;
    left: 0px;
    height: 95vh;
    background-image: 
      url('/./images/bannerImg1.jpg'), 
      url('/./images/bannerImg2.jpg'), 
      url('/./images/bannerImg3.jpg'),
      url('/./images/bannerImg4.jpg');
    background-position: top left, top right, bottom left, bottom right;
    background-repeat: no-repeat;
    background-size: 50vw 50vh;
    margin-bottom: 50px;
  }
  .ctaCont {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #ffffff;
    padding: 15px 50px;
    font-family: var(--headingFont);
    border-radius: var(--mainBorderRadius);
    border: var(--mainBorder);
  }
  .ctaBtn {
    text-align: center;
    font-size: 1.5em;
  }
  .arrowDown {
    position: absolute;
    top: 80vh;
    left: 50%;
    transform: translateX(-25%);
  }
  article {
    margin-bottom: 80px;
  }
  .imageCards {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
  @media screen and (max-width: 900px) {
    .imageCards {
      overflow-x: auto;
      justify-content: left;
      margin-right: 30px;
    }
  }


</style>

<div class="landingBanner">
  <div class="ctaCont">
    <h1>
      Beste<br />
      Backwaren<br />
      Beliebt &<br />
      Bekannt<br />
    </h1>
    <h1 class="ctaBtn"><CtaBtn value="Bestellen" route="#Bestellen" /></h1>
  </div>
  <svg class="arrowDown" xmlns="http://www.w3.org/2000/svg" width="29.25" height="29.25" viewBox="0 0 29.25 29.25">
    <g id="Icon_ionic-ios-arrow-dropdown" data-name="Icon ionic-ios-arrow-dropdown" transform="translate(-3.375 -3.375)">
      <path id="Pfad_1" data-name="Pfad 1" d="M10.378,14.815a1.362,1.362,0,0,0,0,1.92l6.729,6.708a1.356,1.356,0,0,0,1.87.042l6.63-6.609a1.355,1.355,0,1,0-1.912-1.92L18,20.566l-5.7-5.759A1.356,1.356,0,0,0,10.378,14.815Z" fill="#fff"/>
      <path id="Pfad_2" data-name="Pfad 2" d="M3.375,18A14.625,14.625,0,1,0,18,3.375,14.623,14.623,0,0,0,3.375,18ZM26.747,9.253A12.37,12.37,0,1,1,9.253,26.747,12.37,12.37,0,1,1,26.747,9.253Z" fill="#fff"/>
    </g>
  </svg>
</div>

<article>
  <ImageSection {...imageSectionValues[0]} />
  <ImageSection {...imageSectionValues[1]} />
  <ImageSection {...imageSectionValues[2]} />
</article>

<h1 class="marginTop heading">weiteres</h1>

<section class="imageCards">
  <ImageCard {...imgCardValues[0]} />
  <ImageCard {...imgCardValues[1]} />
  <ImageCard {...imgCardValues[2]} />
</section>

<h1 class="heading marginTop">Anregungen? Wünsche?</h1>

<h3 class="heading">Wir freuen uns auf Ihre Nachricht
  und antworten schnellstmöglich!</h3>

<Formular />