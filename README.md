### Task 8 kyu

[Task link](https://www.codewars.com/kata/5601c5f6ba804403c7000004)

The medians of a triangle are the segments that unit the vertices with the midpoint of their opposite sides. The three medians of a triangle intersect at the same point, called the barycenter or the centroid. Given a triangle, defined by the cartesian coordinates of its vertices we need to localize its barycenter or centroid.

The function bar_triang() or barTriang or bar-triang, receives the coordinates of the three vertices A, B and C as three different arguments and outputs the coordinates of the barycenter O in an array [xO, yO]

This is how our asked function should work: the result of the coordinates should be expressed up to four decimals, (rounded result).

You know that the coordinates of the barycenter are given by the following formulas.

For additional information about this important point of a triangle see at: (https://en.wikipedia.org/wiki/Centroid)

Let's see some cases:

barTriang([4, 6], [12, 4], [10, 10]) ------> {8.6667, 6.6667}

barTriang([4, 2], [12, 2], [6, 10] ------> {7.3333, 4.6667}

The given points form a real or a degenerate triangle but in each case the above formulas can be used.

Enjoy it and happy coding!!


### My solution

```Java

class Barycenter {

    public static double[] barTriang(double[] x, double[] y, double[] z)
    {
        double a = (x[0] + y[0] + z[0]) / 3;
        double b = (x[1] + y[1] + z[1]) / 3;

        double aa = (double)Math.round(a * 10000d) / 10000d;
        double bb = (double)Math.round(b * 10000d) / 10000d;

        double [] c = {aa, bb};
        return c;
    }
}

```

### Favourite solution from code-wars

```Java
import java.text.DecimalFormat;

class Barycenter {

    public static double[] barTriang(double[] x, double[] y, double[] z)
    {
        double[] coordinates = new double[2];

        for(int i=0;i<2;i++){
            coordinates[i] = Double.parseDouble(new DecimalFormat("##.####").format((x[i]+y[i]+z[i])/3));
        }

        return coordinates;
    }
}

```

This is the most popular solution and I guess the easiest that I saw. 

# Have a nice day!