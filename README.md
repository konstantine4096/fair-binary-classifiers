# fair-binary-classifiers
This Athena code explores fairness metrics by automating the generation of binary classifiers with SMT solvers. 

To load the code, start Athena and type: 

`load "fair_classifiers";;`

To try searching for a model that has accuracy over 0.8, do:

`(impose [(accuracy > 0.8)])`

To impose predictive parity, possibly along with a minimum accuracy (say 0.6), do:

`(impose [predictive-parity (accuracy >= 0.6)])`

To rule out trivial models and make sure that there's at least one positive and one negative prediction, do:

`(impose [(PPOS > 0) (PNEG > 0) ... <other constraints here> ...])`

To search for a model that satisfies equalized odds, do:

`(impose [equalized-odds ... <other constraints here> ...])`

To search for a model that satisfies approximate equalized odds by bounding the difference between either error
rate to be no more than delta, do:

`(impose [(approx-eq-odds delta) ... <other constraints here> ...])`



