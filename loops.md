Best practice when engineering the traversal of some set of data with an unknown bound to it is not to have something leftover that you apply the same operation to after the loop is completed.\
\
Don't do this:
<pre>
var chunkIndex = 0;
do
{
    LiteralBin += remainingBin.Substring(chunkIndex, 5);
    chunkIndex += 5;
} while (remainingBin[chunkIndex] != '0');
LiteralBin += remainingBin.Substring(chunkIndex, 5);
</pre>

Do this instead:
<pre>
int lastChunkIndex;
var chunkIndex = 0;
do
{
    LiteralBin += remainingBin.Substring(chunkIndex, 5);
    lastChunkIndex = chunkIndex;
    chunkIndex += 5;
} while (remainingBin[lastChunkIndex] != '0');
</pre>

The reason is, a common gotcha is to forget about the remnant that comes afterwards. It's also less clean code to have the redundancy of the operation outside of the loop. Engineering everything to be in the same loop keeps things easier to reason with and leads to less errors.
