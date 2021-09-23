# TUD IS sentiment analysis
This Repository containes code to do sentiment analysis for different terms related from information systems research.



## Notes
- Sentiment nicht schwer zu berechnen
- Verwendete Modelle: vader google-cloud
- Idee: vergleich verschiedener Modelle (Google AWS, Microsoft) weil: Modelle unterscheiden sich.
- Bedenken wegen sehr großer anzahl an tweets: wie könnten wir eine Vorauswahl treffen z.B die 100 ersten jede Woche.
- Tweets für Sentimentanalyse kombinieren: nur einen langen Text draus machen.
- Kritischer Punkt: reicht Akademic Product Track

## TODOS
- Gruppierung nach verschiedener "Granularität" ==> Tag, Monat, Jahr
- Limitierungen vorsehen: 1000 Most popular?
    - Versuch: 100 most popular pro tag für 1 Jahr runterladen.
- Recherchieren: Was ist SoTA: Gruppieren und dann Sentiment berechnen, oder Sentiment Berehnen und Scores dann aggregieren.
    - 1. Gruppierung ==> 2. Berechnung spart API-Calls
- Google-Colab aufsetzten
- Grafiken verschönern
    - Matplotlib tunen,
    - eventuell anderes plotting-backend: plotly!?
- Matplotlib-Config einbauen.

## DONES
- Recherche: Ist die Google-NLP-API Mehrsprachig?
    - Ja, aber: Die `analyze_sentiment`-Funktion ist mehrsprachig, die `analyze_entity_sentiment`-Funktion funktioniert nur auf Englisch, andere sprachen führe zu einer Fehlermeldung.
    - Sollten wir uns auf Englische Tweets verlassen, oder "nur" die `analyze_sentiment`-Funktion? ==> `analyze_sentiment`Funktion
- Einbindung Twitter-API "Academic Track"
    - Credentials bekommen; funktionieren soweit.
- Billing Google-NLP-API auf FG umgestellt.
- 'Kleine' Dokumentation erstellt (Sinn und Zweck des Tools)

## Sinn und Zweck des Tools

Mit dem Tool kann das Sentiment für einen Begriff über einen Zeitabschnitt in einem Liniendiagramm dargestellt werden. Das Sentiment soll die vorherrschende emotionale Stimmung darstellen, um zu erkennen, ob der Autor eine positive, negative oder neutrale Einstellung hat. Das Sentiment wird dabei auf Basis von Tweets zu dem gesuchten Begriff errechnet. Das Sentiment der Tweets berechnet die Google Cloud Natural Language API. Ziel ist es einen Überblick über die allgemeine Stimmung zu verschiedenen Themen zu bekommen und wie sich diese Stimmung im Zeitverlauf verändert.
Da es für viele Begriffe sehr viele Tweets gibt, die nicht alle Analysiert werden können, werden die 1000 populärsten Tweets für jeden Tag zusammengefasst. Für die zusammengefassten Tweets wird das Sentiment berechnet und in die Grafik aufgenommen. Es ist auch möglich die Tweets für jede Stunde zusammen zu fassen und ein Sentiment dafür zu berechnen.
Google ermöglicht zwei Arten der Sentiment Analyse zum einen die Berechnung des generellen Sentiments und zum anderen die Berechnung des Sentiments für eine Entität des Textes. Entitäten sind dabei Eigennamen oder Gattungsnamen. Beispiel: Bei einer Analyse eines Textes über einen Sportler kann zum einen das allgemeine Sentiment über den Text errechnet werden. Es ist allerdings auch möglich den Namen des Sportlers als Entität zu nutzen. Google versucht dann die emotionale Stimmung im Text gegenüber dem Sportler also der Entität zu berechnen. Da Google die Sentiment Analyse pro Entität momentan nur in Englisch, Japanisch, Spanisch unterstützt wird in diesem Tool auf das allgemeine Sentiment zurückgegriffen. Das Tool ist zunächst auf Englisch, Deutsch, Französisch und Spanisch begrenzt kann aber erweitert werden auf alle Sprachen die Google Cloud Natural Language API unterstützt.
Google errechnet zwei Werte, die das Sentiment ausdrücken. Der Wert score gibt die allgemeine emotionale Tendenz eines Dokuments an und liegt zwischen -1 und 1. Der Wert magnitude gibt die allgemeine Stärke der (sowohl positiven als auch negativen) Stimmung im jeweiligen Text zwischen 0.0 und +inf an.

## Performance
Für den Suchbegriff „artificial intelligence“ für die letzten 12 Monate braucht das Tool xx min um die Tweets herunter zu laden, das Sentiment zu berechnen und die Grafik darzustellen.