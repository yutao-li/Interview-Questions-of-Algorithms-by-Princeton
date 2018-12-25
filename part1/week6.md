## Hash Tables
1.4-SUM. Given an array a[] of nn integers, the 4-SUM problem is to determine if there exist distinct indices i, j, k, and l such that a[i]+a[j]=a[k]+a[l]. Design an algorithm for the 4-SUM problem that takes time proportional to n^2(under suitable technical assumptions).

store all possible sum of two integers to hash table, if the position to insert that already contains a sum, check if they are equal, if so, there exist.

2.Hashing with wrong hashCode() or equals(). Suppose that you implement a data type OlympicAthlete for use in a java.util.HashMap.
<pre>
Describe what happens if you override hashCode() but not equals().
Describe what happens if you override equals() but not hashCode().
Describe what happens if you override hashCode() but implement public boolean equals(OlympicAthlete that) instead of public boolean equals(Object that).
</pre>

https://www.geeksforgeeks.org/override-equalsobject-hashcode-method/
in terms of the third question, the problems could be subtle.please refer to http://users.csc.calpoly.edu/~gfisher/classes/102/info/howToOverrideEquals.html  
<pre>
When you override any method you must match the method name, return type, and parameter types exactly.  For the equals method, it must be this:

public boolean equals(Object other)
{
   // Logic here to be discuss below...
}

Notice that the parameter type is Object - it must be Object or you will have overloaded equals instead of overriding it.  The errors that can occur when you do this are subtle.  Your code will work correctly much of the time but fail some of the time.  This is due to polymorphism and runtime binding of methods.  The affect is that, depending on the type of the parameter being passed to equals, sometimes your equals method will execute and sometimes the one in Object (performing strict reference equality) will be execute which, you recall, performs reference equality not logical equality.
</pre>
