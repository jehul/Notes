# Notes: Discussion CS131 Week 6

Prolog Tips and Tricks for the Homework.

Some Prolog built-ins:

     append(List1, List2, List_Result) :
     succeeds if the concatenation of the lists results in List_Result

     Observations: notice how in Prolog we can just as easliy provide
     predicates with a List_Result and get back every combination of
     lists that result in List_Result. We can use predicates backwards,
     forwards, and in every direction in between!


     member(Element, List) : succeeds if Element is in the List.
     memberchk(Element, List): only succeeds once -> how? The "Cut" (!) operator that's how!

     permutation(List1, List2) : succeeds if permutation
     	Observation: potentially useful in our homework but you have to worry about
		     cost of a permutation


     length(List, Length) : succeeds if Length is length is length of list

     nth(N, List, Element): succeeds if Nth argument of List is the Element

     	    Notice here if we make N a variable we will loop through the list!

	    ?- nth(X, [1,2,3], Element).

	    X = 1 ? ;

	    X = 2 ? ;

	    X = 3 ? ;

	    no



     maplist(Goal, List) : succeeds if coal can be applied to all elements of list

           ThOts -

	   maplist(>(5) , [1,2,3,4]).  %here >(5) means all elements are less than 5

	   		perhaps useful to measure height of towers in homework?!?



FINITE DOMAIN SOLVER:
       Its just a class of premade predicates used to define your search space
       of numbers to a finite range (ie. 0 - 268435455)

       so whats different?
       	  in vanilla prolog we were searching the entire number space. Here with FD
	  we are defining a finite search space.



	fd_domain(X, L) : removes from the domain of X values that are not in L

		     ?- fd_domain(X, [1,2,3]).

		     X = _#2(1..3)   %This is saying X can take a value between 1 and 3



	fd_all_different(L) : all items in list must be different values

			 HINT HINT -> probably useful for homework
			     you can make a row or column be uniquely ordered!




My implementation (To be confirmed):
   1) ensure all rows are filled with different elements
   2) ensure all rows are visible contrained to the count
   3) find the transpose of the matrix and apply the above
      This way we can deal with columns too!


	   

