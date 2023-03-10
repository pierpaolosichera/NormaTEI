# NormaTEI
NormaTEI è un software per il controllo del contenuto di uno o più file XML.

## Ambiente
NormaTEI è stato sviluppato utilizzando 4th Dimension.
Tra le molteplici caratteristiche della piattaforma 4D sono stati sfruttati il supporto nativo XML con la libreria Xerces di Apache Foundation e l’accesso alla struttura tramite lo standard DOM (Document Object Model).

## Installazione
Per utilizzare NormaTEI:

#### Windows
  - scarica la cartella Windows; estrai l'archivio compresso nella cartella che preferisci e poi esegui il file NormaTEI.exe;

#### MacOSX 
  - scarica la cartella MacOSX; estrai il file DMG che trovi compresso nella cartella Installer. Dopo l'installazione, nalla cartella /Applicazioni/4D v18.X/ apri il file 4D.app; scegli poi "File -> Open -> Local application ->" e apri il pacchetto NormaTEI.4dbase.

## Specifiche XML-TEI
Nella finestra di avvio cliccare sullo spazio "XML folder", per scegliere la cartella contenente i file XML e premi il tasto "Importa"
Se hai gia importato delle lettere, visualizzare i risultati senza eseguire una nuova importanzione col pulsante in basso "Apri le lettere gia importate"
A questo punto, NormaTEI caricherà tutti i file XML contenuti nella cartella, generando una lista che elenca:
  - il file dove è presente quel tag;
  - il percorso completo;
  - il tag;
  - gli attributi di quel tag;
  - i valori degli aattributi.

In alto viene mostrato il numero di risultati totale.
In basso viene mostrato il numero di valori distinti per ogni colonna.
Su tale elenco è possibile effettuare delle ricerche inserendo una parte del testo da cercare nei riquadri gialli in alto.
