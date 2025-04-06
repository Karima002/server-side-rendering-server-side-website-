
# Qatar Museums - Fabrique
Qatar Museums wil een online collectie-ervaring bieden aan bezoekers. De opdracht is om een homepage te ontwerpen en ontwikkelen met een canvas dat objecten uit een API toont. Daarnaast is ons ook de opdracht gegeven om een detailpagina en een filterpagina te maken.

Live link: https://server-side-rendering-server-side-website-m3f8.onrender.com/

## Beschrijving

### Responsive
Voor het responsive maken van de website heb ik verschillende breakpoints gebruikt. De layout voor een grote scherm bestaat uit 4 kolommen. Bij een breakpoint van 480px worden er 3 kolommen getoond. Bij een breedte lager dan 480px worden 2 kolommen getoond. 

![image](https://github.com/user-attachments/assets/2d96e049-a204-4674-aae0-4124f42e24a3)


## Ontwerpkeuzes

### Layout van images
De images moeten elkaar aansluiten. Bij het gebruik van een grid en flex layout komen er rechte rijen te staat, terwijl de bedoeling van de canvas is dat de images elkaar aansluiten. Hierdoor heb ik ervoor gekozen om een [column count](https://developer.mozilla.org/en-US/docs/Web/CSS/column-count) te gebruiken. In code ziet het er als volgt uit:
https://github.com/Karima002/server-side-rendering-server-side-website-/blob/72079bed77af45f1ff4d21b5f603673e4e02dfb4/public/styles/style.css#L101-L111

### Hover effect
Zowel de afbeeldingen als de header hebben een hover effect. Dit is een vorm van feedforward voor de gebruiker dat er een actie kan volgen na het klikken. 

https://github.com/user-attachments/assets/480a0f9c-8456-46cb-90c4-c803fb402f40

## View-transition
Tussen het navigeren van de detailpagina naar de homepagina is een view-transition toegepast.

https://github.com/user-attachments/assets/316d07eb-5d7a-4226-8d60-2c41cf11d110


## Installatie

### Het inladen van de images uit de api

De data van de images worden opgehaald met een fetch() vanuit de Api. De code gaat pas verder als de data is opgehaald (await).  Deze data wordt doorgegeven aan liquid met response.render. Api kan worden gezien als een variabel die de data (apiResponseJSON.data) doorgeeft liquid.


https://github.com/Karima002/server-side-rendering-server-side-website-/blob/eaabfc43564f954784a576a6cfbe369cf529e6d8/server.js#L24-L32

### Het renderen van de afbeelding in liquid
In de for-loop in liquid `{% for artwork in api %}` wordt elk item in api waangeduid met artwork. API komt van de variable in de server.js: dit bevat de data van de API. `{{ artwork.id }}` vult de ID van het kunstwerk in. Als de ID van een kunstwerk 42 is, zal de URL /object/42 zijn. De basis-URL `https://fdnd-agency.directus.app/assets/` is van de API-server waar de afbeeldingen zijn opgeslagen.


https://github.com/Karima002/server-side-rendering-server-side-website-/blob/fbddb7fdc9d3586c1603fd546c4b311e46383894/views/index.liquid#L7-L17

## Licentie

This project is licensed under the terms of the [MIT license](./LICENSE).
