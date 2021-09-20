## Map的Value排序

map的默认排序是根据其key值进行排序。而map的数据是基于pair的，pair已经重载过了<符号，因此我们不可以用重载的方式对其进行排序。

由于map也是一种stl，因此在对 map进行排序时，可以用vector包起来排序。具体操作如leetcode的451和1636，vector<pair<T,T>> vec(map.begin(),map.end());

## String的查找问题

从右侧开始查找为rfind()函数，此外还有find_last_not_of(),find_first_not_of(),find_last_of(),find_first_of()作用如函数名所示