# State and Zip Code Program
Language: Racket (scheme)

This program stores state zip codes as a list of sublists. Each sublist describes single range of zip codes in a given state.
All of the state information is hashed into a hash table.
The hash table is a vector and each position in the vector is a bucket (list).
Each bucket contains zero or more state lists.
Each state list looks like this: (state name, state abbreviation, low zip, high zip).

The Hash function receives a two-character state abbreviation and which returns an index into a vector.
The hash function distributes the states uniformly.
One is added to the number in the bucket each time a state abbreviation hashes to the bucket.
It Examines the table to make sure the distribution looks uniform. The hash function will be chnaged if it isn't. A prime number is chosen for the size of the table.

The buildTable function uses the zipcodes list to build a hash table containing the state information.

The "reasonableZip?" function is passed the hashTable, a state abbreviation, and a zip code. It returns #t (true) if the zip is in range for the given state, otherwise it returns #f (false).

The user will be prompted to enter a state and a zip code.
