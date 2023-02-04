generate_mutations
==================

.. function:: generate_mutations(sequence, sites)

Generate all possible mutations at given protein sequence sites.

:param sequence: A string representing the original protein sequence.
:type sequence: str
:param sites: A list of integers representing the sites to mutate.
:type sites: list of int
:return: A list of strings representing the mutated protein sequences.
:rtype: list of str

Example
-------

>>> sequence = 'MKLKDFEKVEKLFD'
>>> sites = [2, 5, 9, 12]
>>> generate_mutations(sequence, sites)
['MAKLDFEKVEKLFD',
 'MALKDFEKVEKLFD',
 'MILKDFEKVEKLFD',
 'MVLKDFEKVEKLFD',
 'MKAKDFEKVEKLFD',
 ...]

