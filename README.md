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
- Colab
    - fehler beheben
    - "Dokumentieren"
- Gruppierung nach Country statt Sprache
- Limitierungen vorsehen: 1000 Most popular?
    - Versuch: 100 most popular pro tag für 1 Jahr runterladen.
- Recherchieren: Was ist SoTA: Gruppieren und dann Sentiment berechnen, oder Sentiment Berehnen und Scores dann aggregieren.
    - 1. Gruppierung ==> 2. Berechnung spart API-Calls

## DONES
- Recherche: Ist die Google-NLP-API Mehrsprachig?
    - Ja, aber: Die `analyze_sentiment`-Funktion ist mehrsprachig, die `analyze_entity_sentiment`-Funktion funktioniert nur auf Englisch, andere sprachen führe zu einer Fehlermeldung.
    - Sollten wir uns auf Englische Tweets verlassen, oder "nur" die `analyze_sentiment`-Funktion? ==> `analyze_sentiment`Funktion
- Einbindung Twitter-API "Academic Track"
    - Credentials bekommen; funktionieren soweit.
- Billing Google-NLP-API auf FG umgestellt.
- 'Kleine' Dokumentation erstellt (Sinn und Zweck des Tools)
    - In `tool`-Notebook eingefügt
- Gruppierung nach verschiedener "Granularität" ==> Tag, Monat, Jahr
- Grafiken verschönert
    - Matplotlib tunen (config von Patrick)