Statistik für Fortgeschrittene

#### Multiple lineare Regression

01. adjusting for confounding
> -> statistische kontrolle bereinigt effekt von prädiktor von Drittvariableneffekt

02. Dummyvariablen
> dummycodierung -> einfacher kontrast
> effektcodierung -> abweichungskontrast

03. Aufnahme von Prädiktoren
>**Einschluss:** alles rein
>**Hierarchisch/Blockwise:** selbst festgelegte reihenfolge oder blocks, deltaR2 + deltaFtest
>       -> **inkrementelle Validität:** ist prädik relevant wenn ich für andere einflussfaktoren und konstrukte kontrolliere
>                -> wie groß ist einfluss
>
>**Schrittweise:** vorwärts/rückwerts statalgoryth (explorativ)
>       -> vorwärts präd höchster korr, rückwärts inlkudiert alle prädiks exkludiert nicht sig zuerst
>       -> rückwerts ist besser

04. Vorausetzungen Multiple lineare Regression
>1. **UV ist metrisch oder dichotom**
>2. **Linearität des Zusammenhangs** (Streudiagram, Prediction Intervalls(blaue linie)
>	  verletzt?: nicht lineare Regression oder Ergänzung quad or kubischer term
>3. **Homoskedastizität** (Streudiagram, trichterförmig?)
>	  verletzt? bootstrap methode oder ausweichen auf andere parameterschätzung
>4. **Normalverteilung der Residuen** (Histogramm, QQ Plot)
>     Ausreißer    (cook-distanz > 1 relevant
>	              Mahalanobis Abstand N>=500 >25 N>=100 >15 N>=30 >11
>	              Zerntrierter Hebelwert 2x oder 3x größer)
>	  verletzt? ausschließen und widerholung = sensitivitätsanalyse                         
>5. **Unabhängigkeit der Beobachtungen** (ergibt sich aus studiendesign, genestet oder messwiederholungen)
>	  verletzt? bias standardfehler -> sig test, typ1 fehler nehmen zu, weniger auf parameterschätzer
>     durbinwatson testet serielle abhängigkeit bzw autokorrelation, nicht geeignet aber sinvoll b zeitreihen
>6. **Prädiktoren korrelieren nicht zu hoch untereinander** (multikolinearität) (Variance Inflation Faktor)
>	  (VIF & tolerance >10 <0.1) präd unkorreliert VIF = 1 (VIF ist unabhängig vom outcome)
>	   Prädiktoren dürfen korrelieren, aber nicht zu stark
>	   (2 odermehr hoch korreliert, nahe 1 entspricht beitrag A dem B)
>	   -> signifikanz & relativer beitrag abhängig von reihenfolge und zufälligen unterschieden
>	   (2 perfekt korreliert) -> fehlermeldung
>	        VIF größer 10, redundande prädiks entfernen
>7. **Additivität**
>	-> kann auch multiplikativ sein, wurde wichtiger prädiktor vergessen, sind geschätzte unique kontributions & 
>      koeffizienten nur schlechte schätzer der populationswerte -> bias & verminderung der validität
>8. **Alle wesentlichen Prädiktorem im Modell berücksichtigt** (Modellspezifikation ist korrekt)   
>	    Graphische Darstellung mittels Directed Acyclic Graphs DAGS 
>	    Kausale überlegung, arten von Variablen

05. Variablentypen
>**Confounder:** eine ursache für prädiktor & outcome, inklusion kontrolliert adequat
>nicht geeignet:
>**Collidor:** X und Y auf Z = gemeinsamer effekt, kontrolle von Z führt zu scheinbarer assoziation von x&y
>**Mediator:** Z ist mediator, effekt läuft über Z, kontrolle fürt zu bestimmung von x aber nicht totalem effekt
>**proxy:** z wird von x beeinflusst, hat aber keinen effekt auf Y, Kontrolle von Z unterschätzt kausal effekt von X, 
>           Z ist messfehler

06. weitere voraussetzung: **Weak exogeneity**
>-> Prädiktoren müssen fehlerfrei gemessen werden und sollen keine zufallsvariablen sein
>   wenn verletzt: errors in variables models/ measurement error models/ Strukturgleichungsmodel(sem)

#### Moderationsanalyse

01. **Centering**
>Vor Bildung des Produkterms wird Konstante von allen werten abgezogen
>tyischerweise mittelwert -> **Mean centering**
>sonst Prädiktor und Interaktion hoch korreliert
>bei zentrierten Prädiktoren gibt intercept wert im outcome bei durschnittlichener
>Ausprägung in prädiktoren an.

02. Zur Interpretation von Interaktionen
>-> **Bedingte effekte (Simple slopes)**
>      Zusammenhang von Prädiktor A & Outcome auf unterschiedlichen Nieveaus (3 stufen; +-1 SD)
>-> **Significane regions**
>     Hinweis bei welchen Werten im Moderator sich zusammenhang ändert (empirische schwellenwerte)

03. Interpretation der Interaktion
>-> wenn **sig werden Haupteffekte nicht** mehr eigenständig interpretiert
>        -> haupteffekte nehmen gleiche Effekte für alle werte in allen anderen Variablen an -> hier nicht korrekt!
>        -> Interaktion bedeutet: Anstieg der Regressionsfläche ist in Richtung von A&B nicht konstant(haupteffekte
>           nehmen aber genau das an) -> keine eigneständige Interpretation von Haupteffekten 

04. Interpretation eines kategorialen & eines metrischen prädiktors
>-> haupteffekt bleibt oft interpretierbar, meancentering aber nur für metrischen prädiktor
>**H1 Metrischer prediktor ist kausale Variable**
>-> unterscheidet sich zusammenhang des prädiktors mit outcome in verschiedenen Gruppen
>         -> Test von reggressionskoeffizienten auf gleichheit in k>=2 gruppen
>         -> Interaktion nicht sig ist metr prädik in beiden gruppen gleichstark
>**H2 Dichotomer Prädiktor ist kausale Variable**
>-> ist größe des mittelwertsunterschieds zwischen Gruppe VG und KG abhängig vom Wert des metischen Prädiktors?
>         -> Test der effektmoderation durch eine Drittvariable
>         -> Ist Interaktion nicht sig, hängt Gruppenunterschied nicht von Moderator ab.


#### Mediation (indirekter effekt)

01. c = c' + a x b
>    **totaler effekt = direct effect + indirect effect**
>    c' = 0 vollständige mediation c' /= 0 partielle mediation

02. **Inconsistent mediation**
>ab (indirect effect) und c (direct effect) haben unterschiedliches vorzeichen, mediator ist suppressorvariable

03. äquivalenzklassen 
>alternative modelle sind stat **äquivalent** wenn sie nicht anhand modelfit oder parameterschätzer statistisch 
>unterschieden werden können

#### Logistische Regression

01. varianten des **Outcomes**
>dichotome, ordinale, Zählvariablen, metrisch aber nicht völlig normalverteilte fehler
>vor allem dichotom extremfall für alm durch diskretheit und beschränktheit

02. logit function für dichotome outcomes
>link function ist logit funktion der logistischen regression aus klasse der generelisierten linearen modelle GenLins
>logistische funktion ist umkehr der logit funktion und zwingt werte in intervall 0,1 --> wahrscheinlichkeiten
>mehrdimensionale regressionsebene befindet sich hier auf ebene der logits

03. odds ratios
>exponentierte Regressionskoeffizienten sind als odds ratio (OR interpretierbar) und zeigen wann wie sich chance für
>y ändert wenn der prädiktor um 1 einheit steigt

04. Parameterschätzung in GenLins
>**maximum likelihood Methode (ML)** statt kleinster quadrate -> bestimmt wahrscheinlichste Parameter angesichts 
>modellierter Verteilung, benötigt dafür likelihoodfunktion, **typischerweise logarithmierte likelihood**
>ML ist kein direktes R2 maß sondern vergleicht log likelihood eines modells ohne (baseline) und mit prädiktoren
>-> ergebnis wird für **omnibustest(durch (liklihoodratio LR)** verwendet LR-/X2 ersetzt ftest in mlr

05. erklärte Varianz
>-> Cox & shell, nagelkerke(besser weil zwischen 0 u 1)
>signifikanztest über wald-test

06. Voraussetzungen
>1.**Linearität zwischen Prädiktor & logit des Outcomes** 
>         -> für dichotome Prädiktoren immer gegeben, 
>         -> metrische wechselwirkung mit eigenem logarithmus soll nicht sig sein und ist dann ausreichend gegeben
>2.**Residuen sind nicht normalverteilt**, 
>         -> einflussreiche fälle aber über cook distanz hebelwerte etc
>3.**Unabhängigkeit der Beobachtungen** 
>         -> abhängigkeit führt zu overdispersion(beobachtete varianz größer als von model erwartet)
>         -> verletzt standardfehler zu klein & sig test zu klein, typ I fehler steigt
>         -> abgeleitet aus untersuchungsdesign
>4.**multikollinearität potentielles problem** 
>         -> (VIF & toleranz)
>5.**unvollständige Information**
>         -> nicht alle merkmalsausprägungen in daten vorhanden (standardfehler steigt, ki unverhältnismüßig groß)
>6.**complete seperation**
>         -> ein kategorialer prädigtor oder kombi erklärt outcome perfekt
>         -> unmögliche parameterschätzung
>        lösung: mehr daten sammeln

07. aufnahme von prädiktoren ins modell
>einschluss hierarchisch/blockwise schrittweise

08. **Multinomiale logistische Regression**
>testet prädiktiven wert der prädiks ind jeder einzelnen ausprägung d outcomes gegen eine gemeinsame referenzkategorie
>-> links vs rechts, gemischt vs rechts

#### ANCOVA(kovarianzanalyse)
>-> kontrolliert für drittvariable (confounder(kovariate) Z hat effekt auf UV und AV)

01. ANCOVA in RCTs
>Verringert Residualvarianz & eliminiert Konfundierung -> effekt wird besser -> **power steigt
>weil UV und confounder unkorreliert sind (randomisierung)**

02. ANCOVA in nicht experimentellen studien
>Residualvarianz veringert aber im regelfal auch erklärte varianz der uv **solange confunder mit UV korreliert
>-> kein powergewinn**

03. idee
>statistisches **Konstanthalten des confounders** im Outcome
>-> mittelwert des confounders wird in regressionsgleichung aufgenommen und werte neu berechnet
>-> was wäre wenn analyse : wäre mittelswersdifferenz in UV ausgefallen wenn alle personen gleichen
>wert im confouder gehabt hätten -> Adjustierte Mittelwerte =/ beobachtete mittelwerte 
>
>aber: Ancova stellt keine Vergleichbarkeit der Gruppen an sich her sonder kontroliert nur für 
>überlappende varianzanteile -> **Gruppen in d drittvariablen nicht vergleichbar**
>Dafür: 
>    -> Matching (ziehung geeigneter teilgruppen) -> Approximiert Randomisierung
>    -> Stratifikation -> teilt drittvariable in strata klein gro0 und überprüft
>    effekt der UV innerhalb jeden stratiums

04. ist drittvariable ein bedeustamer konfundierender faktor
>-> steigt die testmacht, p wert kleiner
>-> präzision der effektschätzer nimmt zu SE kleiner
>-> standardisierter effektschätzer der uv wird größer
>ANCOVA  betrachtet immer idealiserten zustand wenn alle personen den gleichen wert gehabt hätten

05. Vorausetzungen
>01. in **mehrfaktoriellen designs 
>          -> Sphärizität** prüfen
>02. **Homogenität der Steigung der Regressionsgeraden**
>          -> Drittvaraible muss mit AV in allen Gruppen **gleich stark assoziiert** sein
>          -> Verletzung wie korr zwischen Drittvaraible & UV (**typIfehler steigt, testmacht sinkt**)
>          prüfbar durch wechselwirkung zwischen UV & Drittvaraible
>                     -> nicht sig -> hinweis auf homogenität
>                     -> wenn sig andere analyse (multilevel)
>03. **Unabhängigkeit zwischen UV und drittvariable**
>.         -> getestet mittels korr oder test >2gruppen einfaktor anova mit drittvar als av

#### Multilevelmodelle

01. idee
> **hierarchische daten**, alles über level 1 sind **kontextvaraiblen**, ausmaß der variabilität im intercept der 
> kontextvariablen über **Intraklassenkorrelation (ICC)** -> icc hoch sind kontextvariablen von bedeutung und residuen 
> nicht mehr unabhängig

02. MLMs können intercepts & slopes über kontexte variieren
> abweichung von fixen koeeficienten sind random, normalverteilt mit erwartungswert 0 und aus daten geschätzter varianz
> MLM dadurch random-effects/random-coefficient model

03. Prädiktoren auf höheren ebenen 
> -> sagen unterschiede von random intercepts/slopes voraus
> **cross-level direct effect** -> modellierung von Unterschieden im intercept zwischen kontexten
> **cross-level interaction/moderation** -> modellierung von unterschieden im slope zwischen kontexten

04. **keine** vorrausetzung:
> Homogenität d Regressionsgeraden, Abhängigkeit der daten & fehlende werte

05. MLMs stufen
> 0. modell ohne random effects 
> 1. modell mit random intercept
> 2. modell mit random intercept & random slopes (unkorreliert)
> 3. modell mit random korrelierten random intercept & random slopes

06. Schätzmethode
> -> **Maximum Likelihood (ML) vs. restricted ML (REML)**
> -> ML ermöglicht **LR test** für modellvergleiche
> -> REML liefert genauere **schätzer für Varianzen**
> -> AIC & Bic -> kleiner besser -> besserer Datenfit; besseres modell

#### Dimensionsreduction und latente Variablen: (PCA & EFA)

01. Anwendung von hauptkomponentenanalyse **(PCA)** & ExploratorischerFaktorenanalyse **(EFA)**
> 1. **Ergründung der gemeinsamen latenten Struktur von Variablen**
> 2. **Überprüfung der faktoriellen Validität von Fragebögen & Skalen**
> 3. **Informationsreduktion und -verdichtung**

##### Hauptkomponentenanalyse (PCA)
02. Grundlage **Interkorrelationsmatrix** R mit k Variablen
> Quadratische Symmetrische Reele matirix (alles korrelationen)
> -> wird überführt in **Ladungsmatrix** lambda (auch komponentenmatrix)
>           -> Zeilen= variablen; spalten = komponenten
> Transponieren der Ladungsmatrix lambda in lambda t
> -> PVA versucht nun weniger komponenten zu extrahieren als eigentlich möglich wäre
>    um R gut zu reporduzieren

03. Diagonal fit
> erste komponente erklärt nicht alles an varianz sondern anteile/variablen = erklärte gesammtvarainz
>
> positiv definit: alle Eigenwerte > 0
> positiv semidefinit: alle Eigenwerte >= 0

04. offdiagonal-Fit
> Abweichung übriger elemente R - lambdalambdaT

05. Abbruchkriterien
> **ScreeTest** -> komponenten **vor** kick -> uneindeutig
> KaiserGuttmanKriterium -> Komponenten > 1 werden behalten -> führt zu überextraktion; auch zufall ergibt eigenwerte>1
> 
> Parallelanalyse
> Vergleicht Verlauf der beobachteten Eigenwerte mit unkorrelierten Zufallsdaten(viele!) gleiches N & K

06. Rotation
> ändern ladungen der Items & größe der eigenwerte zueinander; winkel ändern auch varianz durch überlappen
> 
> Varimax
> Quartimax
> Oblimin





