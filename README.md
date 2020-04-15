<!--
author:   Your Name
email:    your@mail.org

version:  0.0.1

language: de

narrator: Deutsch Male

comment:  Try to write a short comment about
          your course, multiline is also okay.

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css
script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js

translation: Deutsch  translations/German.md
-->

# LiaScript Tutorial

**Herzlich willkommen zum Crashkurs "LiaScript"!**

Lassen Sie uns mit einer kleinen Umfrage beginnen. Welche Lernformate dominieren in Ihrer Lehre?

+ (A) Tafel und Kreide
+ (B) Powerpointfolien / pdfs
+ (C) Inhalte von Learning Managment Systemen (Moodle, OPAL)
+ (D) keines davon


## Autoren auf Wikipedia.org vs. Lehrende

Was unterscheidet Autoren, die unter [Wikipedia](https://www.wikipedia.de/) aktiv sind, von Lehrenden, die ihre Materialien aufbereiten?

<!--
style="width: 100%; max-width: 660px; display: block; margin-left: auto; margin-right: auto;"
-->
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

<!--
style="width: 100%; max-width: 860px; display: block; margin-left: auto; margin-right: auto;"
-->
```ascii

Version 1.0                           Version 1.1
+--------------------------+          +---------------------------+
| Kurs  Deutsche Literatur |          | Kurs  Deutsche Literatur  |
| Autor Peter Muster       | "Fehler" | Autoren Peter Muster      |
|                          |------>   |         Angelika Maier    |----->
|~~~~~~~~~~~~~~~~~~~~~~~~~~|          |~~~~~~~~~~~~~~~~~~~~~~~~~~~|
| Ab 1756 bereiste Goethe  |---.      | Ab 1786 bereiste Goethe   |--.
| Italien ...              |   |      | Italien ...               |  |
                               |                                     |
                               |                                     |    +----------------------------+
                               |                                     |    | Kurs  German Literature    |
                               |                                     |    | Autoren Peter Muster       |
                               |                                     .--> |         Angelika Maier     |
                               |                                          |         Steve Gray         |
                               |                                          |~~~~~~~~~~~~~~~~~~~~~~~~~~~~|
                               |                                          | In 1786 Goethe traveled to |
                               |                                          | Italy ...                  |
                               |       Version 1.0
                               |      +---------------------------+
                               |      | Kurs  Goethes Welt        |
                               |      | Autoren Peter Muster      |
                               .-->   |         Angelika Maier    |----->
                                      |~~~~~~~~~~~~~~~~~~~~~~~~~~~|
                                      | Während der italienischen |
                                      | Reise ...                 |
```

> Wünschenswert ist eine Wiederverwendbarkeit von Inhalten in unterschiedlichen Kontexten und Formaten.


## Welche Voraussetzungen müssen für diese Vision erfüllt sein?

Der Realisierung der Open Educational Ressources (OER) Idee stehen erhebliche Herausforderungen entgegen:

+ Technische Anforderungen:

    - Loslösung der Inhalte von spezifischen Lehr-Lern-Plattformen
    - Unabhänigkeit von Server-Infrastrukturen, Installationen
    - Komplexe Inhalte bei gleichzeitig intuitiver Bedienung
    - Versionierbare Testdateien

+ Soziale Anforderungen:

    - Umdenken in Bezug auf Lizenzen und Freigaben
