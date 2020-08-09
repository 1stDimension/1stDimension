```mermaid
graph LR
    subgraph feature
    f1-->f2-->f3-->f4
    end
    subgraph source
    s1-->f1
    f4-->s2
    end
    subgraph master
    m0-->s1
    m0-->m1
    s1-->m1
    m1-->m2
    s2-->m2
    end

```

Nodes with id matching:
- *m[0-9]{1,}* are commits with fully build README.md
- *s[0-9]{1,}* are commits from witch new README.md will be build when github action trigger
- *m[0-9]{1,}* are commits that will eventualy be merged to branch **source** but README is not yet ready and could break
(I wonder isn't this an overkill?)