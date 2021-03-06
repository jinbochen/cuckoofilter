Cuckoo Filter
============
Cuckoo filter is a Bloom filter replacement for approximated set-membership queries. While Bloom filters are well-known space-efficient data structures to serve queries like "if item x is in a set?", they do not support deletion. Their variances to enable deletion (like counting Bloom filters) usually require much more space. 

Cuckoo ﬁlters provide the ﬂexibility to add and remove items dynamically. A cuckoo filter is based on cuckoo hashing (and therefore named as cuckoo filter).  It is essentially a cuckoo hash table storing each key's fingerprint. Cuckoo hash tables can be highly compact, thus a cuckoo filter could use less space than conventional Bloom ﬁlters, for applications that require low false positive rates (< 3%).

For details about the algorithm and citations please use this article for now

"Cuckoo Filter: Better Than Bloom" by Bin Fan, Dave Andersen and Michael Kaminsky


Interface
--------
A cuckoo filter supports following operations:

*  Add(key): insert key to the filter
*  Contain(key): return if key is already inserted, it may return false positive results like Bloom filters
*  Delete(key): delete the given key from the filter
*  Size(): return the total number of keys existing in the filter
*  SizeInBytes(): return the filter size in bytes

Repository structure
--------------------
    /src/               

the C++ implementation of cuckoo filter

    /example/test.cc    

an example of using cuckoo filter. To build this example, simply type

    $ make

Authors
-------
Bin Fan <binfan@cs.cmu.edu>

David G. Andersen <dga@cs.cmu.edu>

Michael Kaminsky <michael.e.kaminsky@intel.com> 


