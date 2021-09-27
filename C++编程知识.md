## Map的Value排序

map的默认排序是根据其key值进行排序。而map的数据是基于pair的，pair已经重载过了<符号，因此我们不可以用重载的方式对其进行排序。

由于map也是一种stl，因此在对 map进行排序时，可以用vector包起来排序。具体操作如leetcode的451和1636，vector<pair<T,T>> vec(map.begin(),map.end());

## String的查找问题

从右侧开始查找为rfind()函数，此外还有find_last_not_of(),find_first_not_of(),find_last_of(),find_first_of()作用如函数名所示

## 位运算
在int里面，存储的是数值的补码形式，因此转换为unsigned int时候可以直接相加，才不会产生错误。                
另外，两个数相加可以理解为进位为(a&b)<<1，不进位为a^b（此处符号为亦或），二者作为加数再次相加，直至进位为0

## 深层拷贝与浅层拷贝
读取vector内的元素，如果赋值给其他变量，是将对象复制一份新的。如果直接操作数组元素，是不会产生对象复制的。               
c++中常用的vector容器作为参数时，有三种传参方式，分别如下（为说明问题，用二维vector）：             

function1(std::vector<std::vector<int> > vec)，传值        
function2(std::vector<std::vector<int> >& vec)，传引用            
function3(std::vector<std::vector<int> >* vec)，传指针            
注意，三种方式分别有对应的const形式，不在此讨论。

三种方式对应的调用形式分别为：

function1(vec)，传入值              
function2(vec)，传入引用            
function3(&vec),传入地址      

三种方式的效果分别为：
会发生拷贝构造         
不会发生拷贝构造          
不会发生拷贝构造              

此外，有一点是关于auto的使用，auto用来指代数组的数据的时候发生的是深层复制，传入了值，也就是说是一个临时参数，改变它不会改变数组内部数据！！！
## queue和stack的索引问题
queue和stack不可以索引除了开头和结尾的部分