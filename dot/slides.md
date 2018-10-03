The DOT language
================
Pierce Edmiston

``` dot
digraph {
  a -> b;
}
```

![](slides_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

``` dot
digraph {
  node[shape=circle label=""];
  a -> b;
}
```

![](slides_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` dot
digraph {
  node[shape=circle label=""];
  edge[style=invis];
  a -> b;
}
```

![](slides_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

``` dot
digraph {
  graph[rankdir=LR];
  node[shape=circle label=""];
  a -> b;
}
```

![](slides_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

``` dot
digraph {
  rankdir=LR;
  node[shape=circle label=""];
  a -> b;
}
```

![](slides_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

``` dot
digraph {
  rankdir=LR;
  node[shape=circle label=""];
  a -> {b, c, d, e};
}
```

![](slides_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` dot
graph {
  rankdir=LR;
  layout=circo;
  node[shape=circle label=""];
  a -- {b, c, d, e};
}
```

![](slides_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

``` dot
graph {
  rankdir=LR;
  layout=circo;
  node[shape=circle label=""];
  a -- {b, c, d, e};
  b -- {c, d, e};
  c -- {d, e};
  d -- e;
  
  a[label="Pierce"];
  b[label="Willy"];
  c[label="Ed"];
  d[label="Dan"];
  e[label="Josh"];
}
```

![](slides_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

``` dot
graph {
  rankdir=LR;
  layout=circo;
  node[shape=plaintext label="" fontname=helvetica];
  a -- {b, c, d, e};
  b -- {c, d, e};
  c -- {d, e};
  d -- e;
  
  a[label="Pierce"];
  b[label="Willy"];
  c[label="Ed"];
  d[label="Dan"];
  e[label="Josh"];
}
```

![](slides_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

``` dot
digraph {
  rankdir=LR;
  node[shape=circle label="" style=filled];
  a -> {b, c, d, e};
  a[fillcolor="#8da0cb"]
  c[fillcolor="#fc8d62"]
  b, d, e[fillcolor="#66c2a5"]
}
```

![](slides_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

[James’s sklearn
talk](https://jrbourbeau.github.io/madpy-ml-sklearn-2018/#/0/24)

``` dot
from sklearn import datasets
from sklearn.tree import DecisionTreeClassifier, export_graphviz
import graphviz

# ...

def plot_decision_tree(model: DecisionTreeClassifier):
    iris = datasets.load_iris()
    dot_data = export_graphviz(model, out_file=None,
                               feature_names=iris.feature_names[:2],
                               class_names=iris.target_names,
                               impurity=False,
                               filled=True,
                               rounded=True,
                               special_characters=True)
    graph = graphviz.Source(dot_data)
    return graph
```
