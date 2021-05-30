Fakultät für Informations- und Kommunikationswissenschaft 
Institut für Informationswissenschaft 
MALIS-Master in Library and Information Sciences 
Sommersemester 2021 
Modul WPM T9 
Dozent: Prof. Dr. Konrad Förstner 
Verfasserin: Susanne Gerlach 


# Aufgabe WPM_T9.1 
## Datenintensive Prozesse im Arbeitsalltag - Bestandsaufnahme und Ideenentwicklung 


### 1. Einführung 

In der vorliegenden Ausarbeitung soll betrachtet werden, bei welchen Prozessen des eigenen Berufsalltags die Arbeit mit Daten im Fokus steht und wie sich der Umgang mit diesen Daten dabei gestaltet. Darüber hinaus werden Überlegungen angestellt, an welcher
Stelle beziehungsweise bei welchen konkreten Arbeitsschritten eine Softwarelösung gegebenenfalls zur grundsätzlichen Erleichterung oder auch Zeitersparnis im Prozess beitragen könnte. 
Unter der Prämisse, dass es sich bei den angestellten Überlegungen um Daten bzw. Prozesse aus dem Arbeitsalltag handelt, muss darauf verwiesen werden, dass die Verfasserin nicht an einer Bibliothek oder einer anderen Informationseinrichtung tätig ist.
Der berufspraktische Rahmen betrifft daher einen freien Bildungsträger (IUCM), der in Kooperation mit der Ludwigs-Maximilians-Universität München Deutschkurse für internationale Studierende durchführt und für den die Verfasserin als Projektkoordinatorin 
tätig ist. Auch in diesem Arbeitskontext existieren Aufgaben bzw. Prozesse, bei denen mit großen Datenmengen gearbeitet wird und an denen sicherlich die ein oder andere Optimierung des Workflows vorgenommen werden könnte. Wie diese Prozesse aussehen, soll im
Folgenden gezeigt werden.

### 2. Bestandsaufnahme Arbeit mit Daten am IUCM 
Die intensivste Arbeit mit Daten im eingangs geschilderten Arbeitskontext liegt im Bereich der Kursverwaltung und bezieht sich auf den Umgang mit Studierendendaten. Bei der Anmeldungen zu einem der Deutschkurse werden von den Studierenden zahlreiche
Daten abgefragt (personenbezogene Daten, Selbsteinschätzung Sprachniveau, Zugehörigkeit zu stipendienberechtigten Studienprogrammen, etc.) und von ihnen über ein Online-Registrierungsformular auf der Website des IUCM übermittelt. Diese Daten werden im Anschluss in eine lokal vorliegende Datenbank
(MS Access) synchronisiert. Im Rahmen der Kursorganisation werden die einzelnen Datensätze händisch ergänzt (beispielsweise mit Angaben zu bereits besuchten Kursen, Eingruppierung Niveaustufe, interne Kursnummer, Kursbeitrag) und somit für die Arbeit
zur Kurseinteilung und begleitenden Verwaltung optimiert. Am Ende eines jeden Kurses erfolgt auch die Noten-/ETCS-Vergabe über eine Ergänzung in der Datenbank sowie die Zeugniserstellung über einen DB-Bericht. Da an einem einzelnen Deutschkurs im
Schnitt zwischen 450 und 500 Studierende teilnehmen, kommt bei dieser Arbeit eine große Menge relevanter Daten zusammen. 

### 3. Workflows und Optimierungspotential 
Um im Folgenden Überlegungen zu einer Optimierung bestimmter Prozessschritte anstellen zu können, muss zunächst einmal der betreffende Workflow kurz geschildert werden. Grundsätzlich wird eine Access-Datenbank für drei aufeinanderfolgende Kurse genutzt, den
des Wintersemesters, einen Intensivkurs in den Semesterferien und den des folgenden Sommersemesters. Danach wird eine neue Datenbank aufgesetzt und für die Studierendendaten und die Kursverwaltung genutzt. Einer der wichtigsten Arbeitsschritte bei der 
Kursverwaltung ist der Abgleich, ob ein_e Student_in bereits einen Deutschkurs beim IUCM besucht hat und wenn ja in welchem Sprachniveau, um für den neuen Kurs das korrekte Niveau zu ermitteln. Innerhalb des hier geschilderten "Dreier-Zyklus" und somit 
innerhalb einer einzigen Datenbank ist dies relativ problemlos und komfortabel möglich, da eine entsprechende Datenbank-Abfrage mit den betreffenden Filteroptionen genutzt wird. Allerdings ist bereits hier eine gewisse Fehleranfälligkeit zu erkennen, wenn
beispielsweise ein Filter nicht korrekt gesetzt wurde oder es übersehen wird, einen relevanten Filter beim Abgleich mit auszuwählen. Noch problematischer wird es, wenn zum Start eines neuen Wintersemesters die Kurseinteilung vorgenommen werden soll, da hier dann
zwei Access-Datenbanken geöffnet werden müssen und ein ständiges Hin-und Herwechseln nötig wird. Das Gleiche gilt grundsätzlich für die Überprüfung, ob der_die betreffende Teilnehmer_in beispielsweise im Vorjahr schon einmal an einem Kurs teilgenommen hat und daher
auch nur in der zweiten, älteren Datenbank zu finden ist. Eine ähnlich geartete Schwierigkeit - bei der ggf. sogar mit drei oder mehr geöffneten Datenbanken gearbeitet werden muss - tritt auf, wenn abgeglichen werden soll, ob der*die Teilnehmende zu einem 
stipendienberechtigten Studienprogramm (d.h. das Program übernimmt die Kursgebühr) gehört. Manche dieser Programme übernehmen nur einen oder maximal zwei Deutschkurse und so muss über mehrere zurückliegende Semester geprüft werden, ob und wieviele Kurse die 
betreffende Person bereits besucht hat.Es lässt sich feststellen, dass dieser Prozessschritt des Abgleichs über mehrer Datenbanken und einzelne Abfragen/Teilnehmerformulare hinweg nicht nur, wie geschildert, fehleranfällig, sondern auch enorm zeitaufwendig ist. Hier
würde es sich lohnen, darüber nachzudenken, ob nicht eine automatisierte Lösung zum Abgleich der relevanten Daten gewinnbringend wäre. Die nun im folgenden geschilderte Idee steht dabei unter dem Vorbehalt, ob sie in der Praxis tatsächlich so umsetzbar wäre
und ist daher eher als Gedankenexperiment vor dem Hintergrund des aktuellen Kenntnisstandes der Verfasserin zu verstehen.

MS Access bietet die Möglichkeit, alle Datenbankabfragen auch als CSV-Datei zu exportieren. Relativ unaufwändig wäre es, alle "zentralen Abfragen" (damit ist in diesem Fall die Abfrage gemeint, die alle verfügbaren Daten der Studierenden des jeweiligen Kurses enthält und mit der im 
Prozess schwerpunktmäßig gearbeitet wird) der letzen fünf Jahre zu exportieren. Somit hätte man fünf CSV-Dateien vorliegen, die in der Shell bearbeitbar sind. Interessant wäre es nun, ein Skript zu schreiben, das diese Dateien nach vorgegeben Kategorien/Filtern
durchsucht (beispielsweise Name, Geburtsdatum, Anmeldedatum, Sprachniveau) und dann chronologisch sortiert, so dass auf einen Blick ersichtlich wird, welche_r Teilnehmende in welcher Abfolge welchen Kurs besucht hat. Diese Idee ließe sich auch für weitere 
Aufgabenschritte  anwenden, wenn beispielsweise gemeinsam mit Namen/Geburtsdatum (zu einwandfreien Identifikation der Person) die Zugehörigkeit zu einem Studienprogramm durchsucht und dann ausgespielt würde, so dass auch hier der Abgleich, wie viele 
Kurse die Person bereits besucht hat, auf einen Blick möglich wäre. Theoretisch ließe sich dieses relativ simple Grundprinzip, also das Durchsuchen ausgewählter Filter und die anschließende Anzeige nach einer definierten Reihenfolge, beliebig erweitern und für
andere aktuell oder zukünftig anfallende Aufgaben im Prozess adaptieren. Wie bereits weiter oben angesprochen läge der größte Vorteil einer solchen Software-Lösung wohl in der Effizienzsteigerung und Zeitersparnis. Das Ausführen der Befehle in der Shell sollte
deutlich schneller funktionieren als das Öffnen, Abfragen anwählen und Filter setzen in MS Access, nicht zu sprechen von dem Ausführen dieser Schritte in mehreren parallel geöffneten Datenbanken inklusive Springen zwischen diesen. Zusätzliche dürfte die Gefahr,
relevante Informationen zu übersehen, bei dieser kompakten "Datenanzeige auf einen Blick" geringer ausfallen als bei dem Versuch, sich diese Informationen/Daten aus den verschiedenen Datenbanken zusammenzusuchen.

  
