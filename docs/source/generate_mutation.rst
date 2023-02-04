.. _mutations:

Mutating Protein Sequence
========================

.. code-block:: python

    import itertools

    def generate_mutations(sequence, sites):
        """Generates all possible combinations of mutations at the given protein sequence sites.

        Args:
            sequence (str): The protein sequence.
            sites (list): A list of sites to be mutated.

        Returns:
            list: A list of all possible mutated sequences.

        """
        amino_acids = 'ACDEFGHIKLMNPQRSTVWY'
        mutations = []
        site_combinations = [amino_acids for _ in range(len(sites))]
        for mutation_combination in itertools.product(*site_combinations):
            mutated_sequence = list(sequence)
            for site, amino_acid in zip(sites, mutation_combination):
                mutated_sequence[site] = amino_acid
            mutations.append(''.join(mutated_sequence))
        return mutations

    if __name__ == '__main__':
        import argparse

        parser = argparse.ArgumentParser(description='Generate all possible mutation combinations at given protein sequence sites')
        parser.add_argument('sequence', type=str, help='Protein sequence')
        parser.add_argument('sites', type=int, nargs='+', help='Sites to be mutated')
        args = parser.parse_args()
        print(len(generate_mutations(args.sequence, args.sites)))

The `generate_mutations` function generates all possible combinations of mutations by using the `itertools.product` function to generate a cartesian product of the possible amino acids at each site. The result is a list of all possible mutated sequences, which is returned at the end of the function.

The code can be run from the command line by passing the protein sequence and the sites to be mutated as arguments.

For example:

.. code-block:: bash

    python mutations.py MKLKDFEKVEKLFD 2 5 9 12

This will print the number of mutated sequences generated.


