Problem statement:
------------------

Given a text, how to add tags and remove tags with typescript NODE semantic structure using interval tree.

Tree properties:
-----------

 - Intervals at same level of tree is:
     - Non-overlaping                                                                    (Non-overlapping property)
     - Interval at same level must be sorted                                             (Sorted property)
     - Must be continous, where possible - if intervals can be merged, it must be merged (Merged property)
     - Has a start and stop value              
 - Intervals of child of a node:               
     - Is inside its parents interval                                                    (Inside property)
 - A node can not have a tag that onself have                                          . (Tag property)


Add tag (input: [tag , interval : [start,stop]]):
---------

Main idea: keep track of what is left of interval, while adding parts of interval along with a tag at 
           appropriate places.

1. Because the whole interval in "interval" is to be covered, start position must be found through DFS.
2. A start position is found when one of following is true:
  2.1. Found the smallest interval containing start position
  2.2 Found node of same tag - this is needed to avoid having sub child of same tag.
  2.3 


Remove tag (input : [tag, interval : [start,stop]]):
--------------


Main idea: keep track of what is left of interval, while trying to check if any sub-child has some part of interval 

1. One must use DFS to find tag containing smallest interval with start position.
2. There may be different cases, concerning interval:
     2.1 If remove-interval is inside a tag, start and stop position is simple changed; this is followed with termination of DFS
     2.2 
