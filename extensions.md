Create a static method somewhere ***in the same namespace*** where the first parameter is what the thing is that gets extended. Put ***this*** in front of it:
<pre>public static IEnumerable<string> SplitBy(this string str, int splitNum)</pre>
