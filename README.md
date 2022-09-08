# software_labelling
ICSE2023: Software class labelling

Content of the directory
------------------------

    - app_experiments_spl.py
        main application used to apply the analysis protocols to the SPL graph and
        to collect results and data for plots
    - app_experiments_syntetic_swap.py
        main application used to generate synthetic graphs to apply the analysis protocols and
        to collect results and data for plots
    - experiments.py
        implementation of the loops used to select the nodes using the protocols, apply the
        label propagation algorithm and collect the statistics
    - [netx]
        extensions for networkx library
    - [data] datasets
        '4c00c2ca-component-graph-1-r00-vertices.csv'
        '4c00c2ca-component-graph-1-r00-edges.csv'
            graph representation of the proprietary software

        'jdeps-2.8.0.odem'
            Object Dependency Exploration Model (ODEM) file describing the structure of CDA application
            It contains 21 disconnected nodes, 4 components with 2 nodes, 1 component with 3 nodes and
            a component with only 5 nodes plus the largest component composed by 1213 nodes and 6030 edges.
        'jdeps-2.8.0-connected.odem'
            As 'jdeps-2.8.0.odem' but containing only the largest component (1213 nodes, 6030 edges).

        'jdeps-categories-all.csv'
            Map used to convert Java namespaces in a shorted string
        'jdeps-categories-c5.csv'
            Map used to convert Java namespaces in a 5 different categories
        'jdeps-categories-c7.csv'
            Map used to convert Java namespaces in a 7 different categories
        'jdeps-categories-c9.csv'
            Map used to convert Java namespaces in a 9 different categories

        'spl-results.csv'
            Collected results of the analysis protocols applied to the proprietary software

    - [experiments]
        the directory will contain the csv result files of the experiments

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
