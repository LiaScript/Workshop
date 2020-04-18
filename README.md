<!--
author:   Sebastian Zug & André Dietrich
email:    andre.dietrich@Informatik.tu-freiberg.de
version:  0.0.5
language: de
narrator: Deutsch Male
logo:     logo.jpg

comment:  Demo für den das Webinar vom 16.04.2020 in Freiberg.
          Link zur Aufzeichnung: https://www.youtube.com/watch?v=-JyKxvAkAP0

import: https://raw.githubusercontent.com/liaTemplates/rextester/master/README.md

-->

# LiaScript Workshop

**Herzlich willkommen zum Tutorial "LiaScript"!**

Sebastian Zug, Andrè Dietrich (Technische Bergakademie Freiberg)

--------------------------------------------------

!?[Webinar Aufzeichnung](https://www.youtube.com/watch?v=-JyKxvAkAP0)

--------------------------------------------------

_Ablauf:_

1. Motivation des Konzeptes (10 Min)
2. Tutorial (35-40 Min)
3. Fragen und Feedbacks (10 Min)




## Autoren auf Wikipedia.org vs. Lehrende

Was unterscheidet Autoren, die unter [Wikipedia](https://www.wikipedia.de/)
aktiv sind, von Lehrenden, die ihre Materialien aufbereiten?

<!--style="width: 100%; max-width: 760px; display: block; margin-left: auto; margin-right: auto;"-->
```ascii

        Wikipedia Artikel                  Vorlesungsfolien
        Künstliche Intelligenz             Künstliche Intelligenz
        ------------------------           ------------------------
        826 Autoren - 1 Artikel            n Autoren - n Foliensätze

       \   |   /    | \                              +-+            +-+
        v  v  v     v  v                           ->| |          ->| |
        +----------------+                   +-+     +-+            +-+
     -> | KI ist ein     |\                ->| |
        | Teilgebiet der +-+                 +-+              +-+     +-+
      ^ | Informatik ...   | <-                        +-+  ->| |   ->| |
     /  +------------------+                    +-+  ->| |    +-+     +-+
          ^   ^    ^   ^ ^                    ->| |    +-+
          |    \  /    | |                      +-+                            .
```


## Wie sehe der Wikipedia-Ansatz in Bezug auf Lehrmatierialien aus?

> <!-- style="width: 100%; max-width: 860px; display: block; margin-left: auto; margin-right: auto;" -->
> ```ascii
>
> Version 1.0                           Version 1.1
> +--------------------------+          +---------------------------+
> | Kurs  Deutsche Literatur |          | Kurs  Deutsche Literatur  |
> | Autor Peter Muster       | "Fehler" | Autoren Peter Muster      |
> |                          |------>   |         Angelika Maier    |----->
> |~~~~~~~~~~~~~~~~~~~~~~~~~~|          |~~~~~~~~~~~~~~~~~~~~~~~~~~~|
> | Ab 1756 bereiste Goethe  |---.      | Ab 1786 bereiste Goethe   |--.
> | Italien ...              |   |      | Italien ...               |  |
>                                |                                     |
>                                |                                     |    +----------------------------+
>                                |                                     |    | Kurs  German Literature    |
>                                |                                     |    | Autoren Peter Muster       |
>                                |                                     .--> |         Angelika Maier     |
>                                |                                          |         Steve Gray         |
>                                |                                          |~~~~~~~~~~~~~~~~~~~~~~~~~~~~|
>                                |                                          | In 1786 Goethe traveled to |
>                                |                                          | Italy ...                  |
>                                |       Version 1.0
>                                |      +---------------------------+
>                                |      | Kurs  Goethes Welt        |
>                                |      | Autoren Peter Muster      |
>                                .-->   |         Angelika Maier    |----->
>                                       |~~~~~~~~~~~~~~~~~~~~~~~~~~~|
>                                       | Während der italienischen |
>                                       | Reise ...                 |
> ```
> Wünschenswert ist eine Wiederverwendbarkeit von Inhalten in unterschiedlichen
> Kontexten und Formaten.


## Welche Voraussetzungen müssen für diese Vision erfüllt sein?

Der Realisierung der Open Educational Ressources (OER) Idee stehen erhebliche
Herausforderungen entgegen:

* Technische Anforderungen:

  - Loslösung der Inhalte von spezifischen Lehr-Lern-Plattformen
  - Unabhänigkeit von Server-Infrastrukturen, Installationen
  - Komplexe Inhalte bei gleichzeitig intuitiver Bedienung
  - Versionierbare Textdateien


+ Soziale Anforderungen:

  - Umdenken in Bezug auf Lizenzen und Freigaben


# Tutorial


https://LiaScript.github.io

oder

https://LiaScript.io


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
alert(s);
```
<script>@input</script>


## Teilen und Herrschen (mit Plugins)


```armasm
;nasm 2.11.08

section .data
    hello:     db 'Hello world!',10    ; 'Hello world!' plus a linefeed character
    helloLen:  equ $-hello             ; Length of the 'Hello world!' string

section .text
	global _start

_start:
	mov eax,4            ; The system call for write (sys_write)
	mov ebx,1            ; File descriptor 1 - standard output
	mov ecx,hello        ; Put the offset of hello in ecx
	mov edx,helloLen     ; helloLen is a constant, so we don't need to say
	                     ;  mov edx,[helloLen] to get it's actual value
	int 80h              ; Call the kernel

	mov eax,1            ; The system call for exit (sys_exit)
	mov ebx,0            ; Exit with return code of 0 (no error)
	int 80h;
```
@Rextester.eval(@Nasm)


https://github.com/LiaTemplates/


## (Gimmicks)

Tabellen & Diagramme & Multimedia


                                    Multiline
    1.9 |
        |                 ***
      y |               *     *
      - | r r r r r r r*r r r r*r r r r r r r
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
     -1 +------------------------------------
        0              x-axis               1

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
