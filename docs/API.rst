.. Main API page

.. _API:

API
====

ML-Ensemble estimators behave identically to `Scikit-learn`_
estimators, with one main difference: to properly instantiate an ensemble,
at least on layer, and if applicable a meta estimator, must be added to the
ensemble. Otherwise, there is no ensemble to estimate. The difference
can be summarized as follows. ::

   # sklearn API
   estimator = Estimator()
   estimator.fit(X, y)

   # mlens API
   ensemble = Ensemble().add(list_of_estimators).add_meta(estimator)
   ensemble.fit(X, y)


Ensemble estimators
^^^^^^^^^^^^^^^^^^^

.. currentmodule:: mlens.ensemble

.. autosummary::

   SuperLearner
   Subsemble
   BlendEnsemble
   SequentialEnsemble

Model Selection
^^^^^^^^^^^^^^^

.. currentmodule:: mlens.model_selection

.. autosummary::

   Evaluator

Preprocessing
^^^^^^^^^^^^^

.. currentmodule:: mlens.preprocessing

.. autosummary::

   EnsembleTransformer
   Subset

Visualization
^^^^^^^^^^^^^

.. currentmodule:: mlens.visualization

.. autosummary::

   corrmat
   clustered_corrmap
   corr_X_y
   pca_plot
   pca_comp_plot
   exp_var_plot


For developers
==============

The following base classes are good starting points for building new ensembles.
You may want to study the source code directly.

.. _indexer-api:

Indexers
^^^^^^^^

.. currentmodule:: mlens.base

.. autosummary::

    IdTrain
    BlendIndex
    FoldIndex
    SubsetIndex
    FullIndex
    ClusteredSubsetIndex

.. _estimation-api:

Estimation routines
^^^^^^^^^^^^^^^^^^^

.. currentmodule:: mlens.parallel

.. autosummary::

    ParallelProcessing
    ParallelEvaluation
    Stacker
    Blender
    SubStacker
    SingleRun
    Evaluation
    BaseEstimator


.. _Scikit-learn: http://scikit-learn.org/stable/
