---
layout: default
title: Setup Twitch Spawn
description: "Minecraft Version: 1.16.4/1.16.5 - Single player - Last updated: 11/04/2021"
show_top_links: true
top_link:
  back_url: /minecraft
---

<details>
<summary>▼ Indhold (Klik mig)</summary>

<ul>
<li><a href="#kort-introduktion">Kort Introduktion</a></li>
<li><a href="#requirements">Requirements</a></li>
<li><a href="#installation">Installation</a></li>
<li><a href="#configuration">Configuration</a></li>
<li><a href="#testing">Testing</a></li>
<li><a href="#go-live">Go live</a></li>
<li><a href="#lige-det-sidste">Lige det sidste</a></li>
</ul>

</details>

## Kort Introduktion

<hr/>

Twitch spawn er et mod til minecraft som lytter til live events relatered fra din twitch. Både alerts, donations etc. Du kan læse mere om <a href="https://igoodie.gitbook.io/twitchspawn/" target="_blank">Twitch spawn her</a>
De har også selv en fin guide til at sette det op som du kan finde <a href="https://igoodie.gitbook.io/twitchspawn/basics/getting-started" target="_blank">HER</a>

## Requirements

<hr/>

Vi tager udgangs punk i du har java installeret så du kan spille minecraft.

- <a href="https://curseforge.overwolf.com/" target="_blank">CurseForge</a> - Gør det lettere at installere modded.
- En text editor - Jeg anbefaler <a href="https://notepad-plus-plus.org/downloads/" target="_blank">Notepad++</a> eller <a href="https://code.visualstudio.com/" target="_blank">Visual Studio Code</a>

## Installation

<hr/>

Når du har fået installeret curseforge og åbnet det, skal du finde minecraft på listen og klikke på det.
Nu skal vi lave en custom profil men du skal finde ud af hvilken minecraft version du skal bruge, jeg har 2 forskellige versioner under her da developeren ikke har opdateret det til version 1.16.5 i curseforge.

<details>
<summary style="margin-bottom:0.5rem;">▼ <b>For Version 1.16.4 (Klik mig)</b></summary><br>

Du klikker og laver custom profilen til minecraft version 1.16.4 og seneste forge version.<br>
Du kan kalde den hvad du vil.<br><br>

Når det så er gjort og den er installeret osv, skal du klikke ind på selve profilen og ikke klik spil/play endu.<br>
I højre side ser du en puzzle peice hvor der står add more content, klik den.<br><br>

Nu skal du så søge efter: <b>"TwitchSpawn"</b><br>
Og så klikker du installer.

Nu skal du bare åbne minecraft og launche helt ind til settings etc.

<h4 style="margin-bottom:1rem;"><b>Tillykke du har nu installeret Twitch spawn</b></h4>
</details>

<details>
<summary>▼ <b>For Version 1.16.5 (Klik mig)</b></summary><br>

Du klikker og laver custom profilen til minecraft version 1.16.5 og seneste forge version.<br>
Du kan kalde den hvad du vil.<br>

Du skal nu klikke ind på custom profilen og ikke starte minecraft endu.<br>

Nu skal vi lige hente modded så du kan køre det, du henter det  [HER](https://www.curseforge.com/minecraft/mc-mods/twitchspawn) ved at klikke på download oppe til højre på siden.<br>
Den skulle gerne hente en Jar fil som er modded som vi skal bruge lige om lidt.<br>

Du skal nu gå tilbage til curseforge og klikke på de 3 Dots ved siden af play/spil og klikke open folder.<br>

Din stifinder skulle gerne åbne en mappe med en masse i, du skal nu tage den den jar fil vi lige har hentet og smide i den mappe som hedder mods (Hvis der ikke er en så lav den)<br>

Når det er gjort skal du inde i curseforge åbne spille og launche helt ind til minecraft.<br>

<h4 style="margin-bottom:1rem;"><b>Tillykke du har nu installeret Twitch spawn</b></h4>

</details>

## Configuration

<hr/>

Nu skal vi redigere en del filer så jeg håber du har fået installeret en text editor eller kan bruge notepad.

Vi skal nu tilbage til spil mappen for curseforge versionen med TwitchSpawn. Du skal nu gå tilbage til curseforge og klikke ind på den profil som vi lavde tidligere, (ikke start spillet op men klik ind på profilen) og klikke på de 3 Dots ved siden af play/spil og klikke open folder.

Nu burde du se en masse filer dog skal vi skal ind i denne stig/mappe `../configs/TwitchSpawn`

Du burde nu kunne se 5 filer inde i mappen som vi skal tage et kig på.

<hr/>

Den første fil vi kigger på er `credentials.toml`
Du burde til at starte med at rydde hele filen til at ligne dette.
<pre>
moderatorsTwitch = [ "twitchchannel" ]
moderatorsMinecraft = [ "ingamenavn" ]

[[streamers]]
  minecraftNick = "ingamenavn"
  twitchNick = "twitchchannel"
  platform = "ALTERTprogram"
  token = "YOUR_TOKEN"
  tokenChat = "YOUR_CHAT_TOKEN"
</pre>

Først skal vi lige ændre nogen ting i filen inden vi henter alt andet vi skal bruge for at læse alerts.

Du skal tilføje dit twitch navn i `moderatorsTwitch` & `twitchNick` så twitchchannel istedet er din kanal.<br>
Du skal også ædnre `moderatorsMinecraft` & `minecraftNick` til dit minecraftnavn. OBS Den er case sensistiv så store og små bogstaver GÆLDER for minecraft navne!

Du skal nu ændre `platform` til endten `StreamElements` eller `StreamLabs`, Alt efter hvad du bruger skal du åbne den guide under her som passer til din platform for at hente den token du kan bruge.

<details style="margin-bottom:0.5rem;">
<summary>▼ <b>StreamElements Token</b></summary><br>

Stream elements token finder du her:<br>

Når du har kopiret token skal du smide den i `token`

</details>

<details style="margin-bottom:0.5rem;">
<summary>▼ <b>Stream labs Token</b></summary><br>

Du skal bruge streamlabs api token hvilket du finder her:<br>

Når du har kopiret token skal du smide den i `token`

</details>

Dette er optional, Så hvis du ikke bruger den fjerne du bare linjen.<br>
`tokenChat` er for hvis din chat skal kunne indløse channel points.<br>
Du kan skaffe en her: [https://twitchapps.com/tmi/](https://twitchapps.com/tmi/)<br>
Den token den giver igen smider du bare i `tokenChat`

Nu er credentials sat op. så nu kan vi gå vidre.

<hr/>

Den anden fil vi tager et kig på er `preferences.toml`<br>
Dette er filen som man ligsom i minecraft er for indstillingerne.

Når du åbner filen kan du læse om de forskellige indstillinger. dem vil jeg lade dig selv sætte. dog vil jeg sætte mine preferæncer under her

<details>
<summary>▼ <b>preferences.toml</b></summary><br>

<pre>
  messageDisplay="chat"
  notificationDelay=500
  chatWarnings="disabled"
  notificationVolume=0.4
  indicatorDisplay="disabled"
  autoStart="disabled"
</pre>

</details>

<hr/>

Så 2 filer `messages.title.json`, `messages.subtitle.json` er for de beskeder som dukker op i når du modtager en donation etc. Hvordan det skal stå i minecraft når du modtager det på stream. Så det skal du selv indstille.

<hr/>

Den sidste fil er `rules.default.tsl`, denne fil kort og det lange er der du styre hvad der skal ske i spillet når du eksempel får en ny subscriber, nogen donere bits/penge eller gifted subs, generalt ALT.

Udvikleren bag modded har lavet sit eget sprog til pluginnet så det skulle være det at forstå, jeg linker dog så du kan læse mere om det her så du kan læse hvordan det funger. [https://igoodie.gitbook.io/twitchspawn/twitchspawn-language/tsl-basics](https://igoodie.gitbook.io/twitchspawn/twitchspawn-language/tsl-basics)

For at teste og give dig en ide til hvordan det funger skal du bare slette det hele i filen og smide denne her ind

<pre>
SUMMON minecraft:pig
  ON Twitch Follow
</pre>

Det vi generalt siger her er at når en person følger din kanal skal den spawne en gris.

> Hvis du ønsker hjælp til noget er du altid velkommen til at skriv i support på min discord så svarer jeg hurtigts muligt.

## Testing

<hr/>

Nu hvor vi har fået det hele sat op og gjort det kan du nu åbne minecraft med modded så vi kan teste om det hele funger.

> OBS Dette funger ikke på servere med mindre de har installeret det på serveren og fået sat dine credentials ind.

Lav nu en minecraft verden med creative på og gå ind i den.<br>
Når du så er inde skulle der gerne ticke en box frem der siger om twitch spawn er aktiveret eller deaktiveret. (alt efter om du har autostart til eller ej.)

<hr/>

Der er 2 måder at teste på, alt efter hvilken platform du bruger, hvis du bruger stream elements kan du kun bruge simulate da man ikke kan sende test alerts igennem.

Hvis du har streamlabs gå hen i minecraft og skriv `/ts start` for at starte twich spawn det samme med `/ts stop` så stopper du det.

Hvis det lykkedes vil den komme op og sige det er started.<br>
du kan nu inde på stream labs side og trykke på follow så skulle den gerne når du går tilbage til minecraft have spawned en gris ved dig.

<hr/>

Hvis du tilgengæld bruger streamelements skal du benytte dig at `/ts simulate`, dette kræver ikke at du har twitchspawn som også køre.

Skriv følgende commando `/ts simulate {event:"Twitch Follow"}`
og så skulle den gerne sige hvis det lykkedes eller ej.

<hr/>

Hvis der ikke spawner nogen gris kan det være fordi minecraft navn er forkert eller andre ting. evnt reach out på min discord så finder vi ud af det.

<hr/>

Når du laver ændringer i `rules.default.tsl` skal du ikke lukke spillet ned og op igen, du skal bare stope twitch spawn `/ts stop`, og derefter skrive `/ts reloadcfg` du skulle meget gerne se det poppe op. Hvis er er fejl i filen vil den sige det ellers vil den sige success og du så kan starte igen `/ts start`

## Go live

<hr/>

Nu hvor vi lidt har tested det så er der bare for dig at skrive dine egne rules og have det sjovt.

Når du har det er det bare at gå ind i en single player verden og skrive `/ts start` så du live og den tracker alt hvad der sker på din stream også selv om du er offline.

## Lige det sidste

<hr/>

TILYKKE du har nu sat twitch spawn helt op fra bunden og det meget gerne skulle køre nu.

har du problemer er du altid velkommen til at gå i support og skrive
