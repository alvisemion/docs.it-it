### <a name="wpf-grid-allocation-of-space-to-star-columns"></a>Allocazione di spazio della griglia di WPF per le colonne a stella

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7, WPF sostituisce l'algoritmo usato dal controllo <xref:System.Windows.Controls.Grid> per allocare spazio alle colonne a stella (colonne *). Questo modifica la larghezza effettiva assegnata alle colonne * in diversi casi:<ul><li>Quando una o più colonne * hanno anche una larghezza minima o massima che esegue l'override dell'allocazione proporzionale per tale colonna. (La larghezza minima può derivare da una dichiarazione esplicita MinWidth o da un minimo implicito ottenuto dal contenuto della colonna. La larghezza massima può essere definita solo in modo esplicito da una dichiarazione MaxWidth.)</li><li>Quando una o più colonne * dichiarano un peso * estremamente elevato, maggiore di 10^298.</li><li>Quando i pesi * sono diversi al punto da determinare un'instabilità a virgola mobile (overflow, underflow, perdita di precisione).</li><li>Quando è abilitato l'arrotondamento del layout e il DPI effettivamente visualizzato è sufficientemente elevato.</li></ul>Nei primi due casi, le larghezze generate dal nuovo algoritmo possono essere notevolmente diverse da quelle generate dal vecchio algoritmo; nell'ultimo caso, la differenza sarà di uno o due pixel al massimo. Il nuovo algoritmo consente di risolvere diversi bug presenti nell'algoritmo precedente:<ol><li>L'allocazione totale alle colonne può superare la larghezza della griglia. Ciò può verificarsi quando si alloca spazio a una colonna la cui quota proporzionale è minore rispetto alle dimensioni minime. L'algoritmo alloca le dimensioni minime, riducendo lo spazio disponibile per le altre colonne. Se non sono presenti colonne * da allocare, l'allocazione totale potrebbe essere troppo grande.</li><li>L'allocazione totale può non raggiungere la larghezza della griglia. Questo è il doppio problema di #1, che si verifica quando si effettua l'allocazione a una colonna la cui quota proporzionale è maggiore rispetto alle sue dimensioni massime, senza alcuna colonna * per sfruttare la flessibilità.</li><li>Due colonne * possono ricevere le allocazioni in modo non proporzionale ai loro pesi *. Questa è una versione più lieve di #1/#2, che si verifica durante l'allocazione alle colonne * A, B e C (in questo ordine), dove la quota proporzionale di B viola il suo vincolo min o max. Come in precedenza, lo spazio disponibile alla colonna C si riduce e questa ottiene un'allocazione proporzionale inferiore o superiore rispetto ad A,</li><li>Le colonne con pesi estremamente alti (&gt; 10^298) vengono considerate tutte come se avessero un peso di 10^298. Le differenze proporzionali tra di esse (e tra le colonne con pesi leggermente inferiori) non vengono rispettate.</li><li>Le colonne con pesi infiniti non vengono gestite correttamente. [In realtà non è possibile impostare un peso su infinito, ma si tratta di una limitazione artificiale. Il codice di allocazione stava tentando di gestirlo, ma in un processo non valido.]</li><li>Diversi problemi minori mentre si evita l'overflow, l'underflow, la perdita di precisione e altri problemi analoghi della virgola mobile.</li><li>Le modifiche per l'arrotondamento del layout con un DPI sufficientemente elevato non sono corrette.</li></ol>Il nuovo algoritmo produce risultati che soddisfano i criteri seguenti: A. La larghezza effettiva assegnata a una colonna * non è mai minore della larghezza minima né maggiore della larghezza massima. B. A ogni colonna  <em>a cui non è assegnata la larghezza minima o massima è assegnata una larghezza proporzionale al relativo peso <em>. Per essere precisi, se si dichiara che due colonne hanno rispettivamente una larghezza x</em> e y</em> e se nessuna delle colonne riceve la larghezza minima o massima, le larghezze effettive v e w assegnate alle colonne hanno la stessa proporzione: v / w == x / y. C. La larghezza totale allocata alle colonne * &quot;proporzionali&quot; è uguale allo spazio disponibile dopo avere effettuato l'allocazione alle colonne vincolate (fisse, automatiche e colonne * alle quali viene allocata la loro larghezza min o max). Potrebbe essere pari a zero, ad esempio se la somma delle larghezze minime è superiore alla larghezza disponibile della griglia. D. Tutte queste istruzioni devono essere interpretate in base al layout &quot;ideale&quot;. Quando l'arrotondamento del layout è attivo, le larghezze effettive possono differire dalle larghezze ideali per un massimo di un pixel. L'algoritmo precedente rispettava (A) ma non gli altri criteri nei casi descritti in precedenza. Tutte le affermazioni di questo articolo relative a colonne e larghezze sono valide anche per righe e altezze.|
|Suggerimento|Per impostazione predefinita, le applicazioni destinate alle versioni di .NET Framework a partire dalla 4.7 rilevano il nuovo algoritmo, mentre le applicazioni destinate a .NET Framework 4.6.2 o versioni precedenti rilevano il vecchio algoritmo. Per ignorare l'impostazione predefinita, usare l'impostazione di configurazione seguente:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Tramite il valore 'true' è possibile selezionare il vecchio algoritmo, mentre con 'false' è possibile selezionare il nuovo algoritmo.|
|Ambito|Secondario|
|Versione|4.7|
|Tipo|Ridestinazione|
