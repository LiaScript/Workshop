<!--
author:   Sebastian Zug & André Dietrich
email:    andre.dietrich@Informatik.tu-freiberg.de
version:  0.0.5
language: de
narrator: Deutsch Male
logo:     logo.jpg

comment:  Demo für den das Webinar vom 16.04.2020 in Freiberg.
          Link zur Aufzeichnung: https://www.youtube.com/watch?v=-JyKxvAkAP0

import: https://github.com/liaTemplates/rextester
        https://github.com/liaTemplates/KekuleJS
        https://github.com/liaTemplates/VTK
        https://github.com/liaTemplates/Algebrite


script:
    https://jauhl.github.io/mecEdit/scripts/g2.js
    https://jauhl.github.io/mecEdit/scripts/mec2.min.js
    https://jauhl.github.io/mecEdit/scripts/mecelement/canvasInteractor.js
    https://jauhl.github.io/mecEdit/scripts/mecelement/g2.selector.js
    https://jauhl.github.io/mecEdit/scripts/mecelement/mec.htmlelement.js


email: test@web.de

@mec
<lia-keep>
<MEC-2 width=800 height=600 grid cartesian darkmode x0=385 y0=139 >
@0
</MEC-2>
</lia-keep>
@end

@mec.eval: @mec.eval_(@uid)

@mec.eval_
<script>
let json=`@input`

document.getElementById("@0").innerHTML = "<MEC-2 id='test' width=1530 height=680 grid cartesian darkmode x0=385 y0=139 >" + json + "</MEC-2>"

"LIA: stop"
</script>

<div id="@0"></div>

@end

-->

# Freie Lehr-Lern-Materialien ohne Wenn und Aber

**Die Entwicklung von interaktiven Vorlesungen mit LiaScript**

_Tag der Lehre 2020_

Sebastian Zug, Andrè Dietrich (Technische Bergakademie Freiberg)

--------------------------------------------------

_Ablauf:_

1. Motivation des Konzeptes (10 Min)
2. Tutorial (35-40 Min)
3. Fragen und Feedbacks (10 Min)

> Die Interaktive Version dieser Materialien finden Sie unter ...

--------------------------------------------------

**Herzlich Willkommen!** <!-- style = "color: blue;" -->

## Widerspruch der Digitalen Lehre

                 {{0-1}}
************************************************

![Konflikt](https://raw.githubusercontent.com/liaScript/Workshop/master/img/conflict.png)<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->


************************************************

                  {{1-2}}
************************************************

![Konflikt](https://raw.githubusercontent.com/liaScript/Workshop/master/img/JS.png)<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->

************************************************

                  {{2-4}}
************************************************

![Konflikt](https://raw.githubusercontent.com/liaScript/Workshop/master/img/allAspects.png)<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->

************************************************

                  {{3-4}}
************************************************

```
== Geschichte ==

Die [[Bergakademie]] Freiberg wurde 1765, in der Zeit der [[Aufklärung]], durch
[[Franz Xaver von Sachsen|Prinz Xaver von Sachsen]] nach den Plänen von
[[Friedrich Wilhelm von Oppel]] (1720–1767) und [[Friedrich Anton von Heynitz]]
unter dem Namen ''Kurfürstlich-Sächsische Bergakademie zu Freiberg''
```

![Konflikt](https://raw.githubusercontent.com/liaScript/Workshop/master/img/WikipediaBAF.png)<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->


************************************************

## LiaScript-Konzept

![Konflikt](https://raw.githubusercontent.com/liaScript/Workshop/master/img/LiaScript.png)<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->

Verknüpfung der orthogonalen Zielstellungen über eine erweiterte Beschreibungssprache mit:

+ dynamischen Inhalte zur Umsetzung lehrrelevanter Formate (Quizze, Animationen, Grafiken)
+ einer serverlosen Bearbeitung- und Ausführungsumgebung
+ Schnittstellen zur Erweiterung mittels Plugins und der Integration in etablierte LMS


## Bearbeitungsphasen

    {{0-1}}
************************************************

<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->
`````````

Generierung                    Publikation          Konsum durch Lernende



    | Plugin A                                      ╔══════╡ Browser   ╞══════╗
    |  | Plugin B                           nativ   ║ Digitale Systeme        ║
    v  v                                  +-------> ║ (WiSe 2020)             ║
+---------------------+                   |         ║                         ║
| # Digitale Systeme  |\          .-,(  ),-.        ╚═════════════════════════╝
| (WiSe 2020)         +-+      .-(          )-.
|                       | --> ( Cloud Speicher )    ╔══════╡ OPAL      ╞══════╗
| Fallbeispiele         |      '-(         ).-'     ║ Digitale Systeme        ║
| + ...                 |         '-.( ).-' SCORM   ║ (WiSe 2020)             ║
+-----------------------+                 +-------> ║                         ║
                                          |         ╚═════════════════════════╝
                                          |
                                          |         ╔══════╡ pdfViewer ╞══════╗
                                          | export  ║ Digitale Systeme        ║
                                          +-------> ║ (WiSe 2020)             ║
                                                    ║                         ║
                                                    ╚═════════════════════════╝   .
`````````

************************************************

    {{1-3}}
************************************************

<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->
`````````

Generierung                    Publikation          Konsum durch Lernende

                   ::::::::::::::::::::::::::Feedbacks:::::::::::::::::::::::::::::
                   ::                                                            ::
    | Plugin A     ::                               ╔══════╡ Browser   ╞══════╗  ::
    |  | Plugin B  ::                       nativ   ║ Digitale Systeme        ║  ::
    v  v           vv                     +-------> ║ (WiSe 2020)             ║::::
+---------------------+                   |         ║                         ║  ::
| # Digitale Systeme  |\          .-,(  ),-.        ╚═════════════════════════╝  ::
| (WiSe 2020)         +-+      .-(          )-.                                  ::
|                       | --> ( Cloud Speicher )    ╔══════╡ OPAL      ╞══════╗  ::
| Fallbeispiele         |      '-(         ).-'     ║ Digitale Systeme        ║  ::
| + ...                 |         '-.( ).-' SCORM   ║ (WiSe 2020)             ║::::
+-----------------------+                 +-------> ║                         ║  ::
                                          |         ╚═════════════════════════╝  ::
                                          |                                      ::
                                          |         ╔══════╡ pdfViewer ╞══════╗  ::
                                          | export  ║ Digitale Systeme        ║  ::
                                          +-------> ║ (WiSe 2020)             ║::::
                                                    ║                         ║
                                                    ╚═════════════════════════╝
`````````

************************************************

    {{2-3}}
************************************************

![Konflikt](https://raw.githubusercontent.com/liaScript/Workshop/master/img/GitScreenShot.png)<!--
style="width: 100%; max-width: 560px; display: block; margin-left: auto; margin-right: auto;"
-->

************************************************

# Und nun


... wird des praktisch


## Allgemeine Struktur


## PowerPoint & Sprechen Lernen


         --{{1}}--
Zuerst erscheint eine Tabelle.


          {{1-2}}
| Header 1 | Header 2 | Header 3 |
|:-------- |:-------- |:-------- |
| Item 1   | Item 2   | Item 3   |
| test     |          | Wichtig  |

         --{{2}}--
Und dann eine Liste mit wichtigen Punkten.


           {{2}}
* Dies ist
* eine __kleine__
* Liste {3}{_wichtiger_} Informationen.



    --{{3 Russian Male}}--
Markdown (произносится маркда́ун) — облегчённый язык разметки, созданный с целью
написания наиболее читаемого и удобного для правки текста, но пригодного для
преобразования в языки для продвинутых публикаций (HTML, Rich Text и других).

## Quizfrage?


Hat ihnen das gefallen?

    [[Ja]]
    <script>
      // @input will be replace by the user input
      let input_string = "@input";
      "ja" == input_string.trim().toLowerCase();
    </script>


Wie hat Ihnen der Kurs gefallen?


    [[X]] Gut
    [[X]] Super
    [[ ]] Schlecht
    [[?]] Es gibt zwei mögliche Anworten
    [[?]] Es gibt zwei mögliche Anworten
    [[?]] Die ersten beiden
    ****************************************

    Add a solution explanation __Markdown__!

    $$
       \sum_{i=1}^\infty\frac{1}{n^2}
            =\frac{\pi^2}{6}
    $$

    ****************************************



## Programmieren im Browser


```javascript
var s = "JavaScript syntax highlighting";

console.log(s)

3*33
```
<script>@input</script>


## Teilen und Herrschen (mit Plugins)


https://github.com/liaTemplates





### Chemie

https://github.com/liaTemplates/Kekule

``` @Kekule.molecule3d
<cml xmlns="http://www.xml-cml.org/schema">
  <molecule id="m1">
    <atomArray>
      <atom id="a4" elementType="C" x2="13.1708" y2="37.8126"/>
      <atom id="a11" elementType="N" x2="12.3867" y2="37.557500000000005"/>
      <atom id="a5" elementType="C" x2="13.1708" y2="38.637600000000006"/>
      <atom id="a3" elementType="N" x2="13.8865" y2="37.3986"/>
      <atom id="a14" elementType="C" x2="12.3867" y2="35.91630000000001"/>
      <atom id="a7" elementType="C" x2="11.9012" y2="38.225"/>
      <atom id="a6" elementType="C" x2="13.8865" y2="39.050000000000004"/>
      <atom id="a8" elementType="N" x2="12.3867" y2="38.8926"/>
      <atom id="a2" elementType="C" x2="14.6007" y2="37.8126"/>
      <atom id="a15" elementType="O" x2="11.270199999999999" y2="36.330200000000005"/>
      <atom id="a13" elementType="C" x2="11.9655" y2="35.432300000000005"/>
      <atom id="a21" elementType="H" x2="12.3867" y2="35.2079"/>
      <atom id="a1" elementType="N" x2="14.6007" y2="38.637600000000006"/>
      <atom id="a9" elementType="O" x2="13.8865" y2="39.875"/>
      <atom id="a10" elementType="N" x2="15.3178" y2="37.3986"/>
      <atom id="a16" elementType="C" x2="10.1478" y2="35.91630000000001"/>
      <atom id="a12" elementType="C" x2="10.5778" y2="35.432300000000005"/>
      <atom id="a19" elementType="H" x2="11.9655" y2="35.858000000000004"/>
      <atom id="a17" elementType="H" x2="11.9655" y2="34.88720000000001"/>
      <atom id="a22" elementType="C" x2="10.1478" y2="36.578"/>
      <atom id="a23" elementType="H" x2="10.1478" y2="35.2079"/>
      <atom id="a18" elementType="O" x2="10.5778" y2="34.88720000000001"/>
      <atom id="a20" elementType="H" x2="10.5778" y2="35.858000000000004"/>
      <atom id="a24" elementType="O" x2="9.4322" y2="36.9919"/>
    </atomArray>
    <bondArray>
      <bond id="b25" order="S" atomRefs2="a4 a11"/>
      <bond id="b4" order="D" atomRefs2="a4 a5"/>
      <bond id="b3" order="S" atomRefs2="a4 a3"/>
      <bond id="b23" order="S" atomRefs2="a11 a14"/>
      <bond id="b26" order="S" atomRefs2="a11 a7"/>
      <bond id="b5" order="S" atomRefs2="a5 a6"/>
      <bond id="b8" order="S" atomRefs2="a5 a8"/>
      <bond id="b2" order="D" atomRefs2="a3 a2"/>
      <bond id="b13" order="S" atomRefs2="a14 a15"/>
      <bond id="b12" order="S" atomRefs2="a14 a13"/>
      <bond id="b20" order="S" atomRefs2="a14 a21"/>
      <bond id="b7" order="D" atomRefs2="a7 a8"/>
      <bond id="b6" order="S" atomRefs2="a6 a1"/>
      <bond id="b9" order="D" atomRefs2="a6 a9"/>
      <bond id="b1" order="S" atomRefs2="a2 a1"/>
      <bond id="b10" order="S" atomRefs2="a2 a10"/>
      <bond id="b14" order="S" atomRefs2="a15 a16"/>
      <bond id="b11" order="S" atomRefs2="a13 a12"/>
      <bond id="b18" order="S" atomRefs2="a13 a19"/>
      <bond id="b16" order="S" atomRefs2="a13 a17"/>
      <bond id="b15" order="S" atomRefs2="a16 a12"/>
      <bond id="b21" order="S" atomRefs2="a16 a22"/>
      <bond id="b22" order="S" atomRefs2="a16 a23"/>
      <bond id="b17" order="S" atomRefs2="a12 a18"/>
      <bond id="b19" order="S" atomRefs2="a12 a20"/>
      <bond id="b24" order="S" atomRefs2="a22 a24"/>
    </bondArray>
  </molecule>
</cml>
```

### Medizin

https://github.com/liaTemplates/VTK

> Note: This might take a while, to load and render the vti data set within the browser.

@VTK.load(https://data.kitware.com/api/v1/file/58e665158d777f16d095fc2e/download)



### Maschinenbau

``` json @mec
{
  "id":"chaos-pendulums",
  "gravity":true,
  "nodes": [
    { "id":"A0","x":200,"y":400,"base":true },
    { "id":"A1","x":280,"y":480,"m":2 },
    { "id":"B1","x":279,"y":481,"m":2 },
    { "id":"C1","x":278,"y":482,"m":2 },
    { "id":"D1","x":277,"y":483,"m":2 },
    { "id":"A2","x":360,"y":560,"m":3 },
    { "id":"B2","x":359,"y":561,"m":3 },
    { "id":"C2","x":358,"y":562,"m":3 },
    { "id":"D2","x":357,"y":563,"m":3 },
    { "id":"A3","x":440,"y":640,"m":4.7 },
    { "id":"B3","x":439,"y":641,"m":4.7 },
    { "id":"C3","x":438,"y":642,"m":4.7 },
    { "id":"D3","x":437,"y":643,"m":4.7 }
  ],
  "constraints": [
    { "id":"a1","p1":"A0","p2":"A1","len":{ "type":"const" } },
    { "id":"a2","p1":"A1","p2":"A2","len":{ "type":"const" } },
    { "id":"a3","p1":"A2","p2":"A3","len":{ "type":"const" } },
    { "id":"b1","p1":"A0","p2":"B1","len":{ "type":"const" } },
    { "id":"b2","p1":"B1","p2":"B2","len":{ "type":"const" } },
    { "id":"b3","p1":"B2","p2":"B3","len":{ "type":"const" } },
    { "id":"c1","p1":"A0","p2":"C1","len":{ "type":"const" } },
    { "id":"c2","p1":"C1","p2":"C2","len":{ "type":"const" } },
    { "id":"c3","p1":"C2","p2":"C3","len":{ "type":"const" } },
    { "id":"d1","p1":"A0","p2":"D1","len":{ "type":"const" } },
    { "id":"d2","p1":"D1","p2":"D2","len":{ "type":"const" } },
    { "id":"d3","p1":"D2","p2":"D3","len":{ "type":"const" } }
  ],
  "views": [
    { "show":"pos","of":"A3","as":"trace","id":"view1","stroke":"rgba(255,0,0,.5)" },
    { "show":"pos","of":"B3","as":"trace","id":"view2","stroke":"rgba(0,255,0,.5)" },
    { "show":"pos","of":"C3","as":"trace","id":"view3","stroke":"rgba(255,255,0,.5)" },
    { "show":"pos","of":"D3","as":"trace","id":"view4","stroke":"rgba(255,0,255,.5)" }
  ]
}
```

### Mathematik

https://github.com/liaTemplates/Algebrite

```
(3 * x - 5x)^3 * (x + x)

60!
```
@Algebrite.eval



```
f=sin(t)^4-2*cos(t/2)^3*sin(t)

f=circexp(f)

defint(f,t,0,2*pi)
```
@Algebrite.eval





## Fun avec Sprachen


    {{|>}}
Hallo und Willkommen zum LiaScript Sprach-Kurs für Fortgeschrittene.


    {{|> UK English Male}}
Hello and welcome to the LiaScript language course for advanced learners.


### Sprachen Lernen


| English                                | German               | Russian                                 | Arabic male               | Arabic female               |
| -------------------------------------- |:-------------------- |:--------------------------------------- |:------------------------- | --------------------------- |
| {!> UK English Female}{I go}           | {!>}{ich gehe}       | {!> Russian Male}{я хожу}               | {!> Arabic Male}{أذْهبُ}  |                             |
| {!> UK English Female}{you go}         | {!>}{du gehst}       | {!> Russian Male}{ты ходишь}            | {!> Arabic Male}{تذْهبُ}  | {!> Arabic Female}{تذْهبين} |
| {!> UK English Female}{he/she/it goes} | {!>}{er/sie/es geht} | {!> Russian Male}{он / она / оно ходит} | {!> Arabic Male}{يذْهبُ}  | {!> Arabic Female}{تذْهبُ}  |
| {!> UK English Female}{we go}          | {!>}{wir gehen}      | {!> Russian Male}{мы ходим}             | {!> Arabic Male}{نذْهبُ}  |                             |
| {!> UK English Female}{you go}         | {!>}{ihr geht}       | {!> Russian Male}{вы ходите}            | {!> Arabic Male}{تذْهبون} | {!> Arabic Female}{تذْهبْن} |
| {!> UK English Female}{they go}        | {!>}{sie gehen}      | {!> Russian Male}{они ходят}            | {!> Arabic Male}{يذْهبون} | {!> Arabic Female}{يذْهبْن} |

### Sprachen Lernen II
<!--
@play: {!> @0}{<span style="display: none">@1</span>}
@en: @play(UK English Male,@0)
@de: @play(Deutsch Male,@0)
@ru: @play(Russian Female,@0)
@ar: @play(Arabic @0,@1)
-->


| go        |         EN          |         DE          |            RU             |      AR male      |      AR female      |
| --------- |:-------------------:|:-------------------:|:-------------------------:|:-----------------:|:-------------------:|
| I         |      @en(I go)      |    @de(ich gehe)    |        @ru(я хожу)        | @ar(Male,أذْهبُ)   |                     |
| you       |     @en(you go)     |    @de(du gehst)    |      @ru(ты ходишь)       | @ar(Male,تذْهبُ)   | @ar(Female,تذْهبين) |
| he/she/it | @en(he/she/it goes) | @de(er/sie/es geht) | @ru(он / она / оно ходит) | @ar(Male,يذْهبُ)   | @ar(Female,تذْهبُ)   |
| we        |     @en(we go)      |   @de(wir gehen)    |       @ru(мы ходим)       | @ar(Male,نذْهبُ)   |                     |
| you       |     @en(you go)     |    @de(ihr geht)    |      @ru(вы ходите)       | @ar(Male,تذْهبون) | @ar(Female,تذْهبْن)  |
| they      |    @en(they go)     |   @de(sie gehen)    |      @ru(они ходят)       | @ar(Male,يذْهبون) | @ar(Female,يذْهبْن)  |


## Spaß mit Tabellen


                                    Multiline
    1.9 |
        |                 ***                      (* Punkte)
      y |               *     *                    (r rot)
      - | r r r r r r r*r r r r*r r r r r r r      (B BLAU)
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
     -1 +------------------------------------
        0              x-axis               1




| Multiline |  Punkte |   Blau |   rot |
| ---------:| -------:| ------:| -----:|
|    0.0277 |      -1 | -0.356 | 0.611 |
|    0.1111 |      -1 | -0.356 | 0.611 |
|    0.1666 |      -1 | -0.356 | 0.611 |
|    0.2500 | -0.6777 | -0.356 | 0.611 |
|    0.3055 | -0.3555 | -0.356 | 0.611 |
|    0.3333 | -0.0333 | -0.356 | 0.611 |
|    0.3611 |  0.2888 | -0.356 | 0.611 |
|    0.3888 |  0.6111 | -0.356 | 0.611 |
|    0.4166 |  0.9333 | -0.356 | 0.611 |
|    0.4722 |  1.2555 | -0.356 | 0.611 |
|    0.5000 |  1.2555 | -0.356 | 0.611 |
|    0.5277 |  1.2555 | -0.356 | 0.611 |
|    0.5833 |  0.9333 | -0.356 | 0.611 |
|    0.6111 |  0.6111 | -0.356 | 0.611 |
|    0.6388 |  0.2888 | -0.356 | 0.611 |
|    0.6666 | -0.0333 | -0.356 | 0.611 |
|    0.6944 | -0.3555 | -0.356 | 0.611 |
|    0.7500 | -0.6777 | -0.356 | 0.611 |
|    0.8333 |      -1 | -0.356 | 0.611 |
|    0.8888 |      -1 | -0.356 | 0.611 |
|    0.9722 |      -1 | -0.356 | 0.611 |



### LinePlot


<!-- data-show data-title="Government expenditure on education (% of GDP)" -->
| Year | Finland |     USA | Germany |   China |
| ---- | -------:| -------:| -------:| -------:|
| 1995 | 6.80942 |         | 4.42079 | 1.84192 |
| 1996 | 6.86052 |         | 4.48319 | 1.85338 |
| 1997 |         |         |         |         |
| 1998 |         |         | 4.45345 | 1.84432 |
| 1999 | 5.86960 |         |         | 1.88803 |
| 2000 | 5.71687 |         |         |         |
| 2001 | 5.84797 |         |         |         |
| 2002 | 6.02477 |         |         |         |
| 2003 | 6.17476 |         |         |         |
| 2004 | 6.16849 |         |         |         |
| 2005 | 6.03605 |         |         |         |
| 2006 | 5.93809 |         | 4.27930 |         |
| 2007 | 5.68608 |         | 4.34302 |         |
| 2008 | 5.84676 |         | 4.40954 |         |
| 2009 | 6.48517 |         | 4.88047 |         |
| 2010 | 6.54070 | 5.42001 | 4.91368 |         |
| 2011 | 6.48200 | 5.22389 | 4.80779 |         |
| 2012 | 7.19254 | 5.19485 | 4.93331 |         |
| 2013 | 7.15848 | 4.94378 | 4.93496 |         |
| 2014 | 7.15155 | 4.98948 | 4.93112 |         |

https://ourworldindata.org/financing-education#all-charts-preview

### BarChart


| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |             02 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |
| Sheep           |           90 |             12 |      95 |
| Human           |           68 |             70 |      10 |


### PieChart


| Music-Style 1994 | Classic | Country | Reggae | Hip-Hop | Hard-Rock | Samba |
|:---------------- | -------:| -------:| ------:| -------:| ---------:| -----:|
| Student rating   |      50 |      50 |    100 |     200 |       350 |   250 |


<!-- data-transpose -->
| Music-Style {0-1}{1994} {1}{2014} |      Student rating |
|:--------------------------------- | -------------------:|
| Classic                           |   {0-1}{50} {1}{20} |
| Country                           |   {0-1}{50} {1}{30} |
| Reggae                            |                 100 |
| Hip-Hop                           | {0-1}{200} {1}{220} |
| Hard-Rock                         | {0-1}{350} {1}{400} |
| Samba                             | {0-1}{250} {1}{230} |

### Radar


| Animal          | weight in kg | Lifespan years | Mitogen |
| --------------- | ------------:| --------------:| -------:|
| Mouse           |        0.028 |             02 |      95 |
| Flying squirrel |        0.085 |             15 |      50 |
| Brown bat       |        0.020 |             30 |      10 |


### HeatMap

<!-- data-type="heatmap"-->
| Seattle |  Jan |  Feb |  Mar |  Apr |  May |  Jun |  Jul |  Aug |  Sep |  Oct |  Nov |  Dec |
| -------:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:| ----:|
|       0 | 40.7 | 41.5 | 43.6 | 46.6 | 51.4 | 56.0 | 60.5 | 61.2 | 57.0 | 50.1 | 44.1 | 39.6 |
|       2 | 40.2 | 40.7 | 42.7 | 45.3 | 50.0 | 54.4 | 58.5 | 59.2 | 55.4 | 49.2 | 43.5 | 39.3 |
|       4 | 39.7 | 40.0 | 41.9 | 44.4 | 48.9 | 53.2 | 57.0 | 57.7 | 54.2 | 48.6 | 43.1 | 38.9 |
|       6 | 39.6 | 39.5 | 41.3 | 44.2 | 49.5 | 54.2 | 57.8 | 57.4 | 53.6 | 48.2 | 42.8 | 38.7 |
|       8 | 39.6 | 39.9 | 42.9 | 47.1 | 52.7 | 57.3 | 61.3 | 61.1 | 56.7 | 49.5 | 43.1 | 38.7 |
|      10 | 41.3 | 42.7 | 46.4 | 50.7 | 56.4 | 60.9 | 65.2 | 65.4 | 60.9 | 52.8 | 45.5 | 40.4 |
|      12 | 43.8 | 46.0 | 49.5 | 53.8 | 59.6 | 64.3 | 69.4 | 69.8 | 65.1 | 56.0 | 47.8 | 42.6 |
|      14 | 45.1 | 47.7 | 51.3 | 55.9 | 61.9 | 66.9 | 72.6 | 73.2 | 67.7 | 57.8 | 48.8 | 43.6 |
|      16 | 44.5 | 47.5 | 51.4 | 55.9 | 62.3 | 67.5 | 73.9 | 74.3 | 68.2 | 57.4 | 47.8 | 42.6 |
|      18 | 42.6 | 44.7 | 48.7 | 53.8 | 60.3 | 65.9 | 72.3 | 72.2 | 64.6 | 53.9 | 46.0 | 41.2 |
|      20 | 42.0 | 43.3 | 46.4 | 50.2 | 56.0 | 61.4 | 66.9 | 66.6 | 60.7 | 52.3 | 45.2 | 40.7 |
|      22 | 41.4 | 42.5 | 45.0 | 48.3 | 53.5 | 58.2 | 63.2 | 63.5 | 58.7 | 51.1 | 44.5 | 40.1 |

### Map


> GeoJson Sammlung: https://code.highcharts.com/mapdata/

<!-- data-type="BarChart" style="height: 700px" -->
| Country                | percent |
| ---------------------- | ------- |
| Albania                | 73.5    |
| Andorra                | 98.9    |
| Armenia                | 72.4    |
| Austria                | 87.9    |
| Azerbaijan             | 79.8    |
| Belarus                | 79.7    |
| Belgium                | 93.9    |
| Bosnia and Herzegovina | 80.8    |
| Bulgaria               | 66.7    |
| Croatia                | 91.5    |
| Cyprus                 | 84.4    |
| Czech Republic         | 87.7    |
| Denmark                | 97.8    |
| Estonia                | 97.9    |
| Finland                | 94.0    |
| France                 | 92.3    |
| Georgia                | 68.1    |
| Germany                | 96.0    |
| Greece                 | 72.9    |
| Hungary                | 89.0    |
| Iceland                | 99.0    |
| Ireland                | 91.9    |
| Italy                  | 92.5    |
| Latvia                 | 87.1    |
| Liechtenstein          | 98.1    |
| Lithuania              | 90.9    |
| Luxembourg             | 97.8    |
| Macedonia              | 79.2    |
| Malta                  | 83.1    |
| Moldova                | 76.1    |
| Monaco                 | 97.5    |
| Montenegro             | 71.5    |
| Netherlands            | 95.6    |
| Norway                 | 98.4    |
| Poland                 | 78.2    |
| Portugal               | 78.2    |
| Romania                | 73.8    |
| Russia                 | 80.9    |
| San Marino             | 60.2    |
| Republic of Serbia     | 73.4    |
| Slovakia               | 84.9    |
| Slovenia               | 79.9    |
| Spain                  | 92.5    |
| Sweden                 | 96.4    |
| Switzerland            | 93.7    |
| Turkey                 | 83.3    |
| Ukraine                | 93.4    |
| United Kingdom         | 94.9    |
| Vatican City           | 60.1    |

### Graph


If the first column and the head of the table are equal, then the interpreter
tries to interpret the content of the table as an adjacency matrix, which
defines a graph. If those values are symetrical according to the diagonal, then
the matrix defines an __undirected graph__.

| Graph |  A  |  B  |  C  |  D  |  E  |
|:----- |:---:|:---:|:---:|:---:|:---:|
| A     |  0  |  1  |  0  |  1  |  0  |
| B     |  1  |  0  |  0  |  1  |  0  |
| C     |  0  |  0  |  0  |  0  |  0  |
| D     |  1  |  1  |  0  |  0  |  1  |
| E     |  0  |  0  |  0  |  1  |  0  |

In contrast to this, if those values differ, then the result is simply an an
__directed graph__, whereby the values define the strength of the line.

| Graph |  A  |  B  |  C  |  D  |  E  |
|:----- |:---:|:---:|:---:|:---:|:---:|
| A     |  0  | 12  |  0  |  1  |  0  |
| B     | -22 |  0  |  0  | 0.4 |  0  |
| C     |  0  |  0  |  0  |  0  |  0  |
| D     |  2  | 12  |  0  |  0  |  1  |
| E     |  0  |  0  |  0  |  2  |  0  |

> Unfortunatelly, self referenceing or multigraphs are currently not supported.

### Sankey

> Gerichteter Graph zur Visualisierung von Materialflüssen:
>
> https://en.wikipedia.org/wiki/Sankey_diagram


<!-- data-type="sankey" -->
| Sankey |  A  |  B  |  C  |  D  |  E  |
|:------ |:---:|:---:|:---:|:---:|:---:|
| A      |     |     |     |     |     |
| B      |  3  |     |     |     |     |
| C      |  1  |  1  |     |     |     |
| D      |     |  1  |  1  |     |     |
| E      |  2  |  1  |  1  |  1  |     |

## Upload ... Wohin?

https://LiaScript.github.io/course/?

oder

https://LiaScript.io/course/?

### GitHub


https://github.com/LiaScript/Workshop


### DropBox



### Moodle und andere LMS


https://github.com/LiaScript/LiaScript-Exporter/

`liaex -i README.md -f scorm1.2 -o Workshop_ --masteryScore 20`


## Weitere Quellen


https://LiaScript.github.io

https://github.com/LiaBooks

https://www.youtube.com/watch?v=w_CRABsJNKA&t=10s

https://www.youtube.com/watch?v=-JyKxvAkAP0

https://www.youtube.com/channel/UCyiTe2GkW_u05HSdvUblGYg


# Fragen
