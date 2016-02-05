fast_count
==========

Usage Example:
iquery -aq "fast_count(A)"




How does the fast count handle overlapping arrays?

In SciDB, in "Array.cpp: ConstChunk* ConstChunk::materialize() const "


if (!getArrayDesc().hasOverlap()) {
                    materializedChunk->setCount(count);
                                }

Therefore, the count is only set if there array does not have overlap. If the count is not set, the chunks are counted
via an iterator.  


Ubuntu (Most of the below packages will be needed to install fast_count)

For SciDB 15.7 on Ubuntu 14.04 use the below. Note if you are building SciDB from source, make sure to install SciDB at /opt/scidb and do NOT use the paradigm4-15.7-dev package:

sudo apt-get install make git scidb-15.7-libboost1.54-dev g++-4.9 gcc-4.9 libpqxx-dev liblog4cxx10-dev liblog4cpp5-dev libpam0g-dev zlib1g-dev ruby-dev build-essential libboost-system-dev gcc gdebi
