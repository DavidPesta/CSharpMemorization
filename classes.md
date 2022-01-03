### Calling base class's constructor:
<pre>
public class ChildClass : ParentClass
{
    public ChildClass(int first, string second, bool third) : base(first, second) // base constructor will always be called first
    {
</pre>

### Getters/Setters:
<pre>
public int BinLength
{
    get { return PacketBin.Length; }
    private set { OtherProp = value; }
}

public string Bar { get; private set; }
</pre>

### Delegates
<pre>
public delegate void Del(string message);
public static void DelegateMethod(string message) { ... }
Del handler = DelegateMethod;
handler("Hello World");
Dictionary<string, Del> Dels = new Dictionary<string, Del>(); // You can maintain a dynamic set of delegates in a collection.
Dels["someDelegate"] = DelegateMethod;
</pre>
