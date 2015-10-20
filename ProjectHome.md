## Introduction ##
The algorithm PrefixSpan (Prefix-projected Sequential Pattern mining), designed by Pei et al.(1), enumerates frequent sequential patterns from a set of sequences. Frequent means that a sequence occurs in no less than N where N is a threshold.

## Download ##
PrefixSpan is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License.
PrefixSpan is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See GNU General Public License for more details.

## Installation ##
### Requirements ###
C++ compiler with STL (Standard Template Library)
### How to install ###
```
tar -xjvf prefinxspanX.X.tar.gz2
cd prefixspanX.X
make
```

## Usage ##
```
./prefixspan [options] input-data
option: 
 -min_sup INTEGER : set minimum support            (default: 1)
 -max_pat INTEGER : set maximum pattern length (default: infinity)
```
## Format of input data ##
Each line represents a transaction which corresponds to a sequence of items. An example for an input data is as follows:
```
3 1 3 4 5
2 3 1
3 4 4 3
1 3 4 5
2 4 1 
6 5 3 
```

## Format of results ##
```
pattern1
(ids)
pattern2
(ids)
pattern3
(ids)
... 
```

Here is an example:
```
1 
(0 1 3 4)
1 3 
(0 3)
1 3 4 
(0 3)
1 3 4 5 
(0 3)
1 3 5 
(0 3)
1 4 
(0 3)
...
```

## This result means: ##
```
FREQUENT SEQUENCE   : TRANSACTION ID : FREQUENCY
1                                        0 1 3 4                    4
1 3                                     0 3                          2
1 3 4                                  0 3                          2
1 3 4 5                               0 3                          2
1 3 5                                  0 3                          2
1 4                                     0 3                          2
```
Each line represents the frequent sequences whose frequency is no less than min\_sup (-min\_sup option) and the size of itemsets is less than or equal max\_pat (-max\_pat option).

### Bibliography ###
(1) PrefixSpan: Mining Sequential Patterns Efficiently by Prefix-Projected Pattern Growth Jian Pei, Jiawei Han, Behzad Mortazavi-asl, Helen Pinto, Qiming Chen, Umeshwar Dayal and Mei-chun Hsu IEEE Computer Society, 2001, pages 215#

%Id: index.html, v 1.1 2008/12/15 0:19 Yasuo Tabei Exp %;
yasuo.tabei at gmail.com