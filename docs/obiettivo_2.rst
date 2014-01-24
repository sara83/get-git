.. _obiettivo_2:

Obiettivo 2: divergere
######################

Usando una convenzione grafica molto comune nella letteratura su git,
potremmo rappresentare la situazione attuale del tuo repository con

    **A**---B

Cioè: ci sono due ``commit``, ``A`` e ``B``. Il ``commit B`` è figlio di
``A`` (il tempo scorre verso destra). Il ``commit`` in grassetto indica
il punto in cui ti trovi attualmente.

Ma che acadrebbe se facessi in questo momento delle modifiche e committassi?
Nulla di grave: il nuovo ``commit C`` appena generato sarebbe
figlio di ``A`` (perché si parte da lì), ma la linea di svilupppo
proseguirebbe divergendo dalla linea ``A---B``.

Cioè, si creerebbe questa situazione

.. code-block:: bash

    A---B
     \
      C     
Prova davvero:

.. code-block:: bash

    echo "ei fu siccome immobile" > README.md git add README.md git
    commit -m "Ecco il commit C"

.. figure:: img/repo1.png

Hai così ottenuto una diramazione, senza ricorrere al meccanismo di copia dei
file utilizzato da SVN al momento della creazione di un branch: il
modello a chiave/valore e puntatori di git rende molto economico
rappresentare una linea di sviluppo che diverge.

Due osservazioni importanti.

La prima per ribadire il concetto che git non ha mai memorizzato i delta
tra i file: ``A``, ``B`` e ``C`` sono snapshot dell'intero progetto. È
molto importante non dimenticarlo, perché ti aiuterà a capire che tutte le
considerazioni che sei abituato a fare con SVN in git
potrebbero non valere.

La seconda, osservazione, potrebbe un po' sorprenderti: le due linee di sviluppo
divergenti che hai appena visto non sono ``branch``. In git i rami sono
dei puntatori dotati di nome, o delle etichette. Ne parlerò nel
prossimo paragrafo: in git i ``branch`` non
sono rami di sviluppo.

:ref:`Indice <indice>` :: :ref:`Obiettivo 3: creare un branch <obiettivo_3>`
