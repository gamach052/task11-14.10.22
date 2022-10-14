###  [Task 7kyu](https://www.codewars.com/kata/566fc12495810954b1000030/train/java)



Take an integer n (n >= 0) and a digit d (0 <= d <= 9) as an integer.

Square all numbers k (0 <= k <= n) between 0 and n.

Count the numbers of digits d used in the writing of all the k**2.

Call nb_dig (or nbDig or ...) the function taking n and d as parameters and returning this count.




### My solution
```Java
class CountDig
{
    public static int nbDig(int n, int d)
    {
        int c=0;

        for(int i=0;i<=n;i++)
        {
            int p=i*i;
            if ((p==0) && (d == 0)){ c++;}
            while(p!=0)
            {
                int l;
                l=p%10;
                if(l==d){
                    c++;
                }
                p=p/10;
            }

        }
        return c;
    }
}
```

### Fav solution

```Java
import java.util.stream.*;
public class CountDig {
    public static int nbDig(int n, int d) {
        return IntStream.range(0, n+1)
                .mapToObj(i -> String.valueOf(i*i))
                .map(s -> s.replaceAll("[^"+d+"]", ""))
                .collect(Collectors.joining())
                .length();
    }
}
 

```
I like this solution because I like it
