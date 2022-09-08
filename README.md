# software_labelling
Supplementary material and data related to paper titled "Software class labeling with semi-supervised predictions on graphs" submitted to ICSE 2023

Content of the directory
------------------------

    - app_experiments_spl.py
        main application used to apply the analysis protocols to the SPL proprietary software's graph and
        to collect results and data for plots
    - app_experiments_syntetic_swap.py
        main application used to generate synthetic graphs to apply the analysis protocols and
        to collect results and data for plots

    - experiments.py
        module used by the two main applications, that implements the loops used to select the nodes using the protocols, apply the
        label propagation algorithm and collect the statistics
    - [netx]
        module extending NetworkX library, that is used by experiments.py module

    - [data] datasets
        '4c00c2ca-component-graph-1-r00-vertices.csv'
        '4c00c2ca-component-graph-1-r00-edges.csv'
            Graph representation of the proprietary software
        'spl-results.csv'
            Results collected from the experiments, using different protocols, carried out on the proprietary software

        'jdeps-2.8.0.odem'
            Object Dependency Exploration Model (ODEM) file describing the structure of CDA software.
            It contains 21 isolated nodes, 4 connected components with 2 nodes, 1 connected component with 3 nodes,
            a connected component with only 5 nodes, and the largest connected component composed by 1213 nodes and 5692 edges.
        'jdeps-2.8.0-connected.odem'
            As 'jdeps-2.8.0.odem' but containing only the largest connected component (1213 nodes, 5692 edges).
        'jdeps-categories-all.csv'
            One-to-one map used to convert Java namespaces into abbreviated names
        'jdeps-categories-c7.csv'
            Map representing the grouping of Java namespaces into 7 different categories

    - [experiments]
         This empty directory is necessarily created, for containing the csv result files when launching the experiments

File formats
------------

    *-vertices.csv/*-edges.csv
        simple format used to serialize a graph, based on two CSV files.
        The file '*-vertices.csv' contains at minimum the column 'id' containing
        an unique id for each node/vertex.
        All other columns are used as extra properties.

        For the experiments, the other important column is 'category', containing
        the node/vertex's classification.

        The file '*-edges.csv' contains at minimum two column: the edges' source and target.
        The column names is used to specify if the graph is directed ('source', 'target')
        or undirected ('id1', 'id2').
        All other columns are used as extra properties.

    *.odem
        ODEM file is a simple XML file, generated by CDA when the application's dependency
        graph is exported.

    *-categories-*.csv
        It is a simple map 'category->Java namespace'. The column 'count' is not used
        (it is the number of classes inside the namespace).

    'spl-results.csv'
        It is the result
