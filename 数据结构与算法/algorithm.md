---

---

[toc]



==数据结构与算法==

```latex
a_{1}
```



# 数据结构

## 数据结构

- ==按照逻辑关系==组织起来的一批数据
- 按一定的==存储方法==把它存储在计算机中
- 在这些数据上定义了一个==运算==的集合



### 数据结构的逻辑结构

| 线性结构 | 非线性结构 |
| -------- | ---------- |
| 线性表   | 树，图     |

![image-20240722215359528](./algorithm.assets/image-20240722215359528-1724411273301-2-1724411275427-4-1724411769020-1-1724411809477-102-1724414108616-1.png)

### 数据的逻辑结构

数据的逻辑结构是从具体问题抽象出来的数学模型，反映了事物的组成结构及事物之间的逻辑关系。它可以通过集合论和图论的视角来描述和分析。

#### 一、数据的数学模型

1. **二元组表示法**：数据的逻辑结构可以用一个二元组 B=(K, R) 来表示。
    - **节点集合 K**：由数据节点（node）组成的有穷集合。每一个节点代表一个数据或一组有明确结构的数据。
    - **关系集合 R**：定义在集合 K 上的一组二元关系（binary relation）。每个关系 r ∈ R 都是 K 上的二元关系，用来描述数据节点之间的逻辑关系。

2. **二元关系**：K 上的二元组是 K 中元素的有序对，记为 <k, k'>（k, k' ∈ K）。K 上的一个关系即为 K 上一些二元组所组成的集合，不同的二元组集合构成不同的关系。

3. **前驱和后继**：如果 r ∈ R，且 k, k' ∈ K，<k, k'> ∈ r，则称 k 为 k' 在关系 r 上的前驱，k' 为 k 在关系 r 上的后继。
    - **开始结点**：没有前驱的结点。
    - **终止结点**：没有后继的结点。

#### 二、示例：教学计划中的课程关系

1. **节点集合 K**：包含许多课程，每门课程都作为一个数据节点。例如，计算机专业的课程节点集合可能包括“程序设计”、“数据结构”等。

2. **关系集合 R**：包含课程之间的各类关系。例如，先修关系 r 可以表示某些课程必须按规定的先后次序开设。
    - **先修关系**：例如，<程序设计, 数据结构> 表示“程序设计”课程是“数据结构”课程的先修课程。

#### 三、结点结构与关系表现

1. **结点结构**：每个结点代表一个数据或一组有明确结构的数据。结点可以包含多种类型的数据项，例如课程的名称、代码、学分等。

2. **关系表现与限制**：
    - **有向关系**：通过有向图表示，例如先修关系。图中的顶点表示课程，边表示课程之间的先修关系。
    - **无向关系**：如果课程之间没有顺序要求，可以用无向图表示。
    - **层次结构**：某些关系可能表现为层次结构，例如课程的先修关系可以形成一棵树状结构。

通过上述内容，我们可以看出数据的逻辑结构如何抽象和描述事物之间的逻辑关系。这种结构在数据管理和分析中具有重要意义，帮助我们理解和处理复杂的数据关系。

### 数据的存储结构

逻辑结构到物理存储空间的==映射==

==计算机主存储器（内存）==

- 非负整数地址编码，相邻单元的集合
  - 基本单位是字节
  - 访问不同地址所需时间基本相同（即随机访问）

![image-20240722215701957](./algorithm.assets/image-20240722215701957-1724411769020-2-1724411809477-103-1724414108616-2.png)



对逻辑结构（K,r），其中$$r\in R$$

- 对结点集K建立一个从K到存储器M的单元的映射:$$K\rightarrow M$$对于每一个节点$$j\in K$$都对应一个唯一的连续存储区域$$c\in M$$

![image-20240722220437383](./algorithm.assets/image-20240722220437383-1724411769020-3-1724411809477-101-1724414108616-3.png)

- 关系元组$$(j_1,j_2)\in r$$

(其中$$j_1,j_2\in K$$是结点)

- 顺序：存储单元的顺序地址（==线性化==）

![image-20240722222520256](./algorithm.assets/image-20240722222520256-1724411809474-54-1724414108616-4.png)

- 链接：指针的地址指向关系（==非线性的结构组织方法==）

![image-20240722222628356](./algorithm.assets/image-20240722222628356-1724411809474-55-1724414108616-6.png)

- 四类：顺序、链接（基础）、索引、散列（重点）

### 数据的存储结构

数据的存储结构是数据在计算机内存或外部存储器中的组织形式，决定了数据的存储和访问方式。常见的存储结构包括线性存储结构和非线性存储结构。

#### 一、线性存储结构

1. **数组**：数据元素按顺序连续存储的一种数据结构。
    - 优点：通过下标快速访问元素。
    - 缺点：插入和删除操作效率低。

    示例：
    ```markdown
    数组：a[0], a[1], a[2], ..., a[n-1]
    ```

2. **链表**：数据元素通过指针链接成链的一种结构。
    - 优点：插入和删除操作高效。
    - 缺点：访问元素需要从头遍历。

    示例：
    ```markdown
    链表：a -> b -> c -> ... -> n
    ```

3. **栈**：只允许在一端进行插入和删除操作的线性结构，遵循后进先出（LIFO）。
    - 主要操作：push（入栈）、pop（出栈）。

    示例：
    ```markdown
    栈：|a|b|c|d|（d 是栈顶）
    ```

4. **队列**：只允许在一端插入，另一端删除的线性结构，遵循先进先出（FIFO）。
    - 主要操作：enqueue（入队）、dequeue（出队）。

    示例：
    ```markdown
    队列：a <- b <- c <- d（a 是队头，d 是队尾）
    ```

#### 二、非线性存储结构

1. **树**：一种层次结构，数据元素存在父子关系。
    - **二叉树**：每个节点最多有两个子节点。
    - **B 树**：一种自平衡的树数据结构，广泛用于数据库和文件系统。

    示例：
    ```markdown
    二叉树：
         a
        / \
       b   c
      / \
     d   e
    ```

2. **图**：由节点和边组成的结构，可以表示复杂的多对多关系。
    - **有向图**：边有方向性。
    - **无向图**：边没有方向性。

    示例：
    ```markdown
    图：
    a -- b
    |  /
    c -- d
    ```

#### 三、存储方式

1. **顺序存储**：数据元素按顺序存储在连续的存储单元中。
    - 优点：存储密度高，易于实现随机访问。
    - 缺点：需要预先分配存储空间，可能造成存储空间浪费。

    示例：
    ```markdown
    顺序存储：a[0], a[1], a[2], ..., a[n-1]
    ```

2. **链式存储**：数据元素存储在任意存储单元，通过指针表示元素之间的逻辑关系。
    - 优点：插入和删除操作灵活，不需要移动大量元素。
    - 缺点：存储密度低，访问速度较慢。

    示例：
    ```markdown
    链式存储：a -> b -> c -> ... -> n
    ```

#### 四、文件存储

1. **文本文件**：以字符为基本单位存储数据，适合存储可以直接显示和编辑的文本内容。
    - 示例：.txt 文件

2. **二进制文件**：以字节为基本单位存储数据，适合存储图像、音频、视频等多媒体数据。
    - 示例：.bin 文件

通过上述内容，我们可以看出数据的存储结构决定了数据的组织方式和访问效率。在实际应用中，应根据具体需求选择合适的数据存储结构，以优化存储和访问性能。

## 抽象数据类型

- 简称==ADT(Abstract Data Type)==
  - 定义了一组运算的数学模型
  - 与物理存储结构无关
  - 使软件系统建立在数据之上（面向对象）

- 模块化的思想的发展
  - 隐藏运算实现的细节和内部数据结构
  - 软件复用

- 抽象数据结构二元组
  - <数据对象D，数据操作P>

- 先定义逻辑结构，再定义运算
  - ==逻辑结构==：数据对象及其关系
  - ==运算==：数据操作（函数）

例子：==栈==



---

![image-20240723103110718](./algorithm.assets/image-20240723103110718-1724411809474-56-1724414108616-5.png)



# 算法特性和简单分类

# 第一单元先略过（概论）

# 线性表

- 线性表简称表，是零歌或多个元素又穷序列，通常可以表示成$$k_0,k_1,…,k_{n-1}$$.
- ![image-20240723103740296](./algorithm.assets/image-20240723103740296-1724411809475-57-1724414108616-7.png)

- 二元组$$B=(K,R),K=\{a_0,a_1,…,a_{n-1}\},R=\{r\}$$

- 有一个唯一的==开始结点==，没有前驱，有一个唯一的直接后继

- 一个唯一的==终止结点==，它有一个唯一的直接前驱，而没有后继

- 其它的结点皆成为内部节点，每一个内部节点都有且仅有一个唯一的直接有前驱，也有一个唯一的直接有后继

  $$<a_i,a_i+1>,a_i是a_{i+1}的前驱，a_{i+1}是a_i的后继$$

- 前驱/后继关系r，具有==反对称性==和==传递性==

![image-20240723105439508](./algorithm.assets/image-20240723105439508-1724411809475-58-1724414108616-8.png)

==特点==

![image-20240723105528545](./algorithm.assets/image-20240723105528545-1724411809475-59-1724414108616-9.png)

## 分类

==按复杂度划分==

- 简单的：线性表、栈、队列、散列表
- 高级的：广义表、多维数组、文件……

==按访问方式划分==

- 直接访问型
- 顺序访问型
- 目录索引型

![image-20240723110207232](./algorithm.assets/image-20240723110207232-1724411809475-60-1724414108616-10.png)

==按操作划分==

- 线性表
  - 所有表目都是同一类型结点的线性表
  - 不限制操作形式
  - 根据存储的不同分为：顺序表，链表

- 栈
  - ==插入和删除==操作都限制在表的==同一端==进行

- 队列

  - ==插入==操作在表的==一端==，==删除==操作在==另一端==

  ==逻辑结构、存储结构、运算有一点不同都是不同的数据结构==

## 线性表的逻辑结构

- 主要属性包括
  - 线性表的长度（预留存储、数据规模）
  - 表头
  - 表尾
  - 当前位置

![image-20240723113820272](./algorithm.assets/image-20240723113820272-1724411809475-61-1724414108616-11.png)

## 线性表的存储结构

==顺序表==

- 按索引值从小到大存放在一篇相邻的连续区域
- 紧凑结构，存储密度为1

![image-20240723113958349](./algorithm.assets/image-20240723113958349-1724411809475-62-1724414108616-12.png)

==链表==

- 单链表![image-20240723114100516](./algorithm.assets/image-20240723114100516-1724411809475-63-1724414108616-13.png)（存储效率不如顺序表，有指针开销)

- 双链表![image-20240723114130908](./algorithm.assets/image-20240723114130908-1724411809475-64-1724414108616-14.png)

- 
- 循环链表![image-20240723114145161](./algorithm.assets/image-20240723114145161-1724411809475-65-1724414108616-15.png)

## 线性表的运算

![image-20240723114335505](./algorithm.assets/image-20240723114335505-1724411809475-66-1724414108616-18.png)

==线性表的类模版==

![image-20240723114407092](./algorithm.assets/image-20240723114407092-1724411809475-67-1724414108616-16.png)

# 顺序表

==也称向量，采用定长的一维存储结构==

- 主要特性
  - 元素的类型相同
  - 元素顺序地存储在连续存储空间中，每一个元素有唯一的索引值
  - 使用常数作为向量长度

- 数组存储
- 读写其元素很方便，通过下标即可指定位置
  - 只要确定了首地址，线性表中任意数据元素都可以随机存取

## 地址的计算

![image-20240725093835436](./algorithm.assets/image-20240725093835436-1724411809475-68-1724414108616-17.png)

## 顺序表类定义

```C++
class arrList:public List<T>{	//顺序表，向量
    private:
    	T* aList;			  //存储顺序表的实例
    	int maxXize;		  //顺序表实例的最大长度
    	int curLen;			  //顺序表实例的当前长度
    	int position;		  //当前处理位置
    public:
    	arrList(const int size){//创建新表，设置表实例的最大长度
            maxSize = size;
            aList =new T[maxSize];
            curlen=position=0;
        }
    	~arrList(){//析构函数，消除该表实例
            delete []aList;
        }
    	
        
}
```

### ==函数接口==

```cpp
void clear(){
    delete []aList;
    curLen=position=;
    aList=new T[maxSize];
}
int length();// 返回当前实际长度
bool append(const T value);//在表尾添加元素value
bool insert(const int p,cont T value);//p位置插入元素value
bool delete(const int p);//删除位置p上元素
bool setValue(const int p,const T value);//设元素值
bool getValue(const int p,T &value)//返回元素
bool getPos(int &p,const Tvalue);//查找元素
};
```

### ==重点讨论==

- 插入元素运算
  - `bool insert(const int p,const T value)`

  ```cpp
  //设元素的类型为T,aList是存储顺序表的数组，maxSize是其最大长度；
  //p为新元素value的插入位置，插入成功则返回true，否则返回false
  template<class T> bool arrList<T>::insert()(const int p,const T value){
      int i;
      if(curLen>=maxsize){
          //检查顺序表是否溢出
          return false;
      }
      if(p<0||p>curLen){
          //检查插入位置是否合法
          return false;
      }
      for(i=curLen;i>p;i--)
          	aList[i]=aList[i-1];
          aList[p]=value;
          curLen++;
      return true;
      
  }
  ```
  
  
  
- 删除元素运算
  - `bool delete(const int p)`
  
  ```cpp
  template<class T>
  bool arrList<T>::delete(const int p){
      int i;
      if(curLen<=0||p<0||p>curLen-1){return false;}
      for(i=p;i<curLen-1;i++){
          aList[i]=aList[i+1];
      }
      curLen--;
      return true;
  }
  ```

### ==算法分析==

- 表中元素的移动
  - 插入：移动`n-i`
  - 删除:移动`n-i-1`
- `i`的位置上插入和删除的概率分别是$$p_i$$ 和$$p_{i}^{'}$$ 
  - 插入的平均移动次数为$$M_i = \sum_{i=0}^{n}(n-i)p_i$$
  - 删除的平均移动次数为$$M_d=\sum_{i=0}^{n-1}(n-i-1)p_i^{'}$$

==特殊情况==

>
>
>- 如果在顺序表中每个位置上插入和删除元素的概率相同，即$$p_i=\frac{1}{n+1},p_i^{'}=\frac{1}{n}$$
>
>- $$
>  M_i=\frac{1}{n+1}\sum_{i=0}^{n}(n-i)=\frac{1}{n+1}(\sum_{i=0}^{n}n-\sum_{i=0}^{n}i)
>   ==\frac{n(n+1)}{n+1}-\frac{n(n+1)}{2(n+1)}=\frac{n}{2}
> $$
>
> $$
>M_d=\frac{1}{n}\sum_{i=0}^{n-1}(n-i-1)=\frac{1}{n}(\sum_{i=0}^{n-1}n-\sum_{i=0}^{n-1}i-n)=\frac{n^2}{n}-\frac{n-1}{2}-1=\frac{n-1}{2}
>$$
>
>- 时间代价为o(n)




==函数具体实现==

```cpp
template <typename T>
class arrList : public List<T> {  // 顺序表，向量
private:
    T* aList;        // 存储顺序表的实例
    int maxSize;     // 顺序表实例的最大长度
    int curLen;      // 顺序表实例的当前长度
    int position;    // 当前处理位置

public:
    arrList(const int size) {  // 创建新表，设置表实例的最大长度
        maxSize = size;
        aList = new T[maxSize];
        curLen = position = 0;
    }

    ~arrList() {  // 析构函数，消除该表实例
        delete[] aList;
    }

    void clear() {  // 清空顺序表
        delete[] aList;
        curLen = position = 0;
        aList = new T[maxSize];
    }

    int length() {  // 返回当前实际长度
        return curLen;
    }

    bool append(const T value) {  // 在表尾添加元素value
        if (curLen >= maxSize) {
            return false;
        }
        aList[curLen++] = value;
        return true;
    }

    bool insert(const int p, const T value) {  // p位置插入元素value
        if (curLen >= maxSize || p < 0 || p > curLen) {
            return false;
        }
        for (int i = curLen; i > p; --i) {
            aList[i] = aList[i - 1];
        }
        aList[p] = value;
        ++curLen;
        return true;
    }

    bool remove(const int p) {  // 删除位置p上元素
        if (p < 0 || p >= curLen) {
            return false;
        }
        for (int i = p; i < curLen - 1; ++i) {
            aList[i] = aList[i + 1];
        }
        --curLen;
        return true;
    }

    bool setValue(const int p, const T value) {  // 设元素值
        if (p < 0 || p >= curLen) {
            return false;
        }
        aList[p] = value;
        return true;
    }

    bool getValue(const int p, T& value) {  // 返回元素
        if (p < 0 || p >= curLen) {
            return false;
        }
        value = aList[p];
        return true;
    }

    bool getPos(int& p, const T value) {  // 查找元素
        for (p = 0; p < curLen; ++p) {
            if (aList[p] == value) {
                return true;
            }
        }
        return false;
    }
};
```

# 链表

- 通过==指针==把它的一串存储结点链接成一个链
- 存储结点由两部分组成：
  - 数据域+指针域（后继地址）

|data | next |

## 分类

### 单链

==简单的单链表==

- 整个单链表：head
- 第一个结点：head
- 空表判断：head=NULL
- 当前节点$$a_1$$:`curr`

![image-20240725185256026](./algorithm.assets/image-20240725185256026-1724411809475-69-1724414108616-21.png)

```cpp
template<class T>class Link{
    public:
    T data;//用于保存结点元素的内容
    Link<T>*next;//指向后继结点的指针
    Link(const T info,const Link<T>*nextValue=NULL){
        data=info;
        next=nextValue;
    }
    Line(const Link<T>*nextValue){
        next=nextValue;
    }
    
}
```

==例子==

```cpp
#include <iostream>

// 定义模板类 Link
template<class T>
class Link {
public:
    T data;                 // 保存节点元素的内容
    Link<T>* next;          // 指向后继节点的指针

    // 构造函数：初始化数据和后继节点指针
    Link(const T info, Link<T>* nextValue = NULL) {
        data = info;
        next = nextValue;
    }

    // 构造函数：仅初始化后继节点指针
    Link(Link<T>* nextValue) {
        next = nextValue;
    }
};

int main() {
    // 创建三个节点
    Link<int> node1(10);  // data = 10, next = NULL
    Link<int> node2(20);  // data = 20, next = NULL
    Link<int> node3(30);  // data = 30, next = NULL

    // 将节点连接成单链表
    node1.next = &node2;  // node1 的 next 指向 node2
    node2.next = &node3;  // node2 的 next 指向 node3

    // 输出链表中的元素
    Link<int>* current = &node1;
    while (current != NULL) {
        std::cout << current->data << " ";
        current = current->next;
    }

    return 0;
}

```

==单链表类定义==

```cpp
template<class T>class lnkList:public List<T>{
    private:
    Link<T>* head,*tail;//单链表的头、尾指针
    Link<T>* setPos(const int p);//第p个元素指针
    public:
    lnkList(int s);//构造函数
    ~lnkList();//析构函数
   	bool isEmpty();//判断链表是否为空
    void clear();//将链表存储的内容清除，成为空表
    int length;//返回此顺序表的当前实际长度
    bool append(const T value);//表尾添加一个元素value,表长度增
    bool insert(const int p,const T value);//位置p上插入一个元素
    bool delete(const int p)//删除位置p上呢元素，表的长度减一
    bool getValue(const int p,T& value)//返回位置p的元素值
    bool getPos(int &p,const T value)//查找值为value的元素
}
```



`lnkList`模板类的具体实现，涵盖了各个方法的功能：

```cpp
#include <iostream>
using namespace std;

// Link类定义，表示单链表的节点
template<class T>
class Link {
public:
    T data;                // 节点的数据
    Link<T>* next;         // 指向下一个节点的指针

    // 构造函数：初始化节点的数据和后继节点指针
    Link(const T& info, Link<T>* nextValue = nullptr)
        : data(info), next(nextValue) {}

    // 构造函数：仅初始化后继节点指针
    Link(Link<T>* nextValue = nullptr)
        : next(nextValue) {}
};

// List类定义，用于表示链表的基本接口
template<class T>
class List {
public:
    virtual ~List() {}
    virtual bool isEmpty() = 0;
    virtual void clear() = 0;
    virtual int length() = 0;
    virtual bool append(const T value) = 0;
    virtual bool insert(const int p, const T value) = 0;
    virtual bool deletePos(const int p) = 0;
    virtual bool getValue(const int p, T& value) = 0;
    virtual bool getPos(int& p, const T value) = 0;
};

// lnkList类定义，单链表的具体实现
template<class T>
class lnkList : public List<T> {
private:
    Link<T>* head;    // 链表头指针
    Link<T>* tail;    // 链表尾指针
    int listSize;     // 链表的长度

    // 返回指向第p个元素的指针
    Link<T>* setPos(const int p) {
        if (p < 0 || p > listSize) return nullptr;  // 检查越界
        Link<T>* temp = head;
        for (int i = 0; i < p; ++i) temp = temp->next;
        return temp;
    }

public:
    // 构造函数
    lnkList(int s = 0) : head(nullptr), tail(nullptr), listSize(s) {}

    // 析构函数
    ~lnkList() { clear(); }

    // 判断链表是否为空
    bool isEmpty() {
        return listSize == 0;
    }

    // 清除链表
    void clear() {
        Link<T>* temp;
        while (head != nullptr) {
            temp = head;
            head = head->next;
            delete temp;
        }
        tail = nullptr;
        listSize = 0;
    }

    // 返回链表的长度
    int length() {
        return listSize;
    }

    // 在表尾添加元素
    bool append(const T value) {
        Link<T>* newNode = new Link<T>(value);
        if (isEmpty()) {
            head = tail = newNode;
        } else {
            tail->next = newNode;
            tail = newNode;
        }
        listSize++;
        return true;
    }

    // 在位置p上插入元素
    bool insert(const int p, const T value) {
        if (p < 0 || p > listSize) return false;  // 检查越界

        if (p == 0) {
            head = new Link<T>(value, head);
            if (tail == nullptr) tail = head;
        } else {
            Link<T>* prev = setPos(p - 1);
            prev->next = new Link<T>(value, prev->next);
            if (prev->next->next == nullptr) tail = prev->next;
        }
        listSize++;
        return true;
    }

    // 删除位置p的元素
    bool deletePos(const int p) {
        if (p < 0 || p >= listSize) return false;  // 检查越界

        Link<T>* temp;
        if (p == 0) {
            temp = head;
            head = head->next;
            if (head == nullptr) tail = nullptr;
        } else {
            Link<T>* prev = setPos(p - 1);
            temp = prev->next;
            prev->next = temp->next;
            if (temp == tail) tail = prev;
        }
        delete temp;
        listSize--;
        return true;
    }

    // 返回位置p的元素值
    bool getValue(const int p, T& value) {
        if (p < 0 || p >= listSize) return false;  // 检查越界

        Link<T>* temp = setPos(p);
        if (temp == nullptr) return false;
        value = temp->data;
        return true;
    }

    // 查找值为value的元素位置
    bool getPos(int& p, const T value) {
        Link<T>* temp = head;
        p = 0;
        while (temp != nullptr && temp->data != value) {
            temp = temp->next;
            p++;
        }
        if (temp == nullptr) return false;
        return true;
    }
};

// 示例使用
int main() {
    lnkList<int> myList;

    myList.append(1);
    myList.append(2);
    myList.append(3);
    myList.insert(1, 4); // 在第1个位置插入值4

    int value;
    for (int i = 0; i < myList.length(); ++i) {
        myList.getValue(i, value);
        cout << value << " ";
    }

    return 0;
}
```

### 代码解释：

1. **`Link`类**：单链表节点的定义，包含数据和指向下一个节点的指针。
2. **`List`类**：一个抽象基类，定义了链表的基本接口。
3. **`lnkList`类**：单链表的具体实现，继承自`List`。包含头尾指针、链表长度等成员，以及各种操作方法。
4. **操作方法**：
   - `setPos`：获取指向第`p`个元素的指针。
   - `isEmpty`：检查链表是否为空。
   - `clear`：清空链表。
   - `length`：返回链表长度。
   - `append`：在链表尾部添加元素。
   - `insert`：在指定位置插入元素。
   - `deletePos`：删除指定位置的元素。
   - `getValue`：获取指定位置的元素值。
   - `getPos`：查找指定值的元素位置。



==带头结点的单链表==

- 整个单链表：`head`
- 第一个结点:$$head->next,head\neq NULL$$
- 空表判断：head->next==NULL

当前节点$$a_1$$:`fence->next`(curr隐含)

![image-20240725190211238](./algorithm.assets/image-20240725190211238-1724411809475-70-1724414108617-22.png)

- 双链表和循环链表的操作类似

# 顺序表和链表的比较

## 总体比较

- 顺序表的主要优点
  - 没有使用指针，不用花费额外开销
  - 线性表元素的读访问非常简洁便利
- 链表的主要优点
  - 无需事先了解线性表的长度
  - 允许线性表的长度动态变化
  - 能够适应经常插入删除内部元素的情况
- 总结
  - 顺序表是存储静态数据的不二选择
  - 链表是存储动态变化数据的良方

- 顺序表
  - 插入、删除运算时间代价O(n),查找则可常数时间完成
  - 预先申请固定长度的连续空间
  - 如果整个数组元素很慢，则没有结构性存储开销
- 链表
  - 插入、删除运算时间代价O(1),但找地i个元素运算时间代价O(n)
  - 存储；利用指针，动态地按照需要为表中新的元素分配存储空间
  - 每个元素都有结构性存储开销

![image-20240725213017535](./algorithm.assets/image-20240725213017535-1724411809475-71-1724414108616-19.png)

![image-20240725213134562](./algorithm.assets/image-20240725213134562-1724411809475-72-1724414108616-20.png)

![image-20240725213302087](./algorithm.assets/image-20240725213302087-1724411809475-73-1724414108617-23.png)

## 练习题

【讨论】求数组最大子数组之和 求数组最大子数组之和       1, -2, 3, 10, -4, 7, 2, -5  和最大的子数组为【3, 10, -4, 7, 2】  输出为该子数组的和18  请分别思考分治法、动态规划法及其效率

### 笨方法

```cpp
#include<iostream>
#include<vector>
using namespace std;
int main(){
    vector<int>nums;
    int n;
    cin >> n;
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        nums.push_back(temp);
    }
    vector<int> dp(nums.size(), 0);
    dp[0] = max(nums[0],0);
    int result = -10000000;
    for (int i = 1; i < n;i++){
        dp[i] = max(dp[i - 1] + nums[i], nums[i]);
        result = max(result, dp[i]);
    }
    cout << result << endl;
}#include<iostream>
#include<vector>
using namespace std;
int main(){
    vector<int>nums;
    int n;
    cin >> n;
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        nums.push_back(temp);
    }
    vector<vector<int>> numm(nums.size(), vector<int>(nums.size(), 0));
    int maxx = 0;
    for (int i = 0; i < n;i++){
     numm[i][i] = nums[i];
     maxx = max(numm[i][i], maxx);
    }
    for (int i = 0; i < n;i++){
        for (int j = i+1; j < n;j++){
            numm[i][j] = numm[i][j - 1] + nums[j];
            maxx = max(numm[i][j], maxx);
        }
    }
    cout << maxx << endl;
}
```

### 动态规划

```cpp
#include<iostream>
#include<vector>
using namespace std;
int main(){
    vector<int>nums;
    int n;
    cin >> n;
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        nums.push_back(temp);
    }
    vector<int> dp(nums.size(), 0);
    dp[0] = max(nums[0],0);
    int result = -10000000;
    for (int i = 1; i < n;i++){
        dp[i] = max(dp[i - 1] + nums[i], nums[i]);
        result = max(result, dp[i]);
    }
    cout << result << endl;
}
```

### 分治法

#### 分治法解决最大子数组和问题

分治法的核心思想是将数组递归地分成两个部分，分别求解每个部分的最大子数组和，然后合并这些部分的解。

##### 步骤详解

1. **基准情况（Base Case）**: 
   - 如果数组只有一个元素，那么最大子数组和就是这个元素。

2. **分割数组（Divide）**: 
   - 将数组分为左右两个部分：`left` 到 `mid` 和 `mid + 1` 到 `right`。
   - 中点 `mid` 的计算方式是 `mid = left + (right - left) / 2`。

3. **递归求解（Conquer）**: 
   - 递归地在左半部分和右半部分分别求解最大子数组和。
   - `left_max`：左半部分的最大子数组和。
   - `right_max`：右半部分的最大子数组和。

4. **计算跨越中点的子数组（Combine）**: 
   - **左侧最大子数组和**：从中点向左扫描，找到最大子数组和。
   - **右侧最大子数组和**：从中点向右扫描，找到最大子数组和。
   - 跨中点的最大子数组和是左侧最大和与右侧最大和的总和。

5. **合并结果**: 
   - 返回左半部分、右半部分和跨越中点部分的最大值。

##### 代码实现（C++）

```cpp
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;
int maxcross(vector<int>nums,int left,int mid,int right){
    int left_sum = INT_MIN;
    int sum = 0;
    for (int i = mid; i >= left;i--){
        sum += nums[i];
        if(sum>left_sum){
            left_sum = sum;
        }
    }
    sum = 0;
    int right_sum = INT_MIN;
    for (int i = mid + 1; i <= right;i++){
        sum += nums[i];
        if(sum>right_sum){
            right_sum = sum;
        }
    }
    return left_sum + right_sum;
}
int maxarraysum(vector<int>nums,int left,int right){
    if(left==right){
        return nums[left];
    }
    int mid = left + (right - left) / 2;
    int left_max = maxarraysum(nums, left, mid);
    int right_max = maxarraysum(nums, mid + 1, right);
    int cross_max = maxcross(nums, left, mid, right);
    return max({left_max, right_max, cross_max});
}
int main(){
    int n;
    cin>>n;
    vector<int> nums;
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        nums.push_back(temp);
    }
    cout << maxarraysum(nums, 0, n-1);
}
```

##### 时间复杂度

- 分治法的时间复杂度为 O(n log n)。在每一级递归中，计算跨中点的最大子数组和需要 O(n) 时间，总共有 O(log n) 级递归。

### 判断链表中有无回路

定义两个指针，一个指针每次移动一个节点，另一个指针每次移动两个节点。如果链表中存在回路，那么快指针最终会追上慢指针，两个指针会相遇。如果链表中不存在回路，那么快指针会先到达链表的末尾，此时我们就可以判断链表中不存在回路。时间复杂度为 O(n)，空间复杂度为 O(1) 。

# 栈

- 栈

  - 运算只能在==表==的一端进行
  - 后进先出
  - 主要操作：进栈和出栈

  ![image-20240727191056721](./algorithm.assets/image-20240727191056721-1724411809475-74-1724414108617-25.png)

 ```cpp
 template<class T>
 class Stack{
     public:
     	void clear();	//变为空栈
     	bool push(const T item);//item 入栈，成功返回真，否则假
     	bool pop(T& item);//返回栈顶内容并弹出，成功返回真，否则假
     	bool top(T& item);//返回栈顶但不弹出，成功返回真，否则假
     	bool isEmpty();//若栈已空返回真
     	bool ifFull();//若栈已满返回真
     
 };
 ```

```cpp
#include <iostream>
#include <vector>

template<class T>
class Stack {
public:
    // 清空栈
    void clear() {
        data.clear();
    }

    // 入栈操作，成功返回 true
    bool push(const T item) {
        data.push_back(item);
        return true;
    }

    // 出栈操作，成功返回 true 并将 item 设置为栈顶元素
    bool pop(T& item) {
        if (isEmpty()) {
            return false; // 栈为空，无法出栈
        }
        item = data.back();
        data.pop_back();
        return true;
    }

    // 查看栈顶元素，成功返回 true 并将 item 设置为栈顶元素
    bool top(T& item) {
        if (isEmpty()) {
            return false; // 栈为空，无法查看栈顶
        }
        item = data.back();
        return true;
    }

    // 判断栈是否为空
    bool isEmpty() {
        return data.empty();
    }

    // 判断栈是否已满（对于使用 std::vector 的实现，一般不设置栈满限制）
    bool ifFull() {
        return false; // 使用 vector 无容量限制，所以总返回 false
    }

private:
    std::vector<T> data; // 使用 vector 作为底层存储
};

```









## ==入栈顺序==

![image-20240727193100971](./algorithm.assets/image-20240727193100971-1724411809475-75-1724414108617-24.png)



引理：设k是最后一个出栈的，那么k把序列一分为二；在k之前入栈的元素，一定比在k之后入栈的元素，要提前出栈！

利用这个引理，递归判断出栈顺序是否合法

### 思考题

- 给定一个入栈序列，和一个出栈序列，请你写出一个程序，判断出栈序列是否合法？

```cpp
#include<iostream>
#include<stack>
#include<vector>
#include<algorithm>
using namespace std;
bool is_legal(vector<int>in_stac,vector<int>out_stac,int left,int right){
    if(in_stac.empty())
        return true;
    if(left==right){
        return in_stac[left] == out_stac[left];
    }
    int last_element = out_stac[right];
    int i = 0;
    while(last_element!=in_stac[i])
        i++;
    vector<int> left_in_stac(in_stac.begin(), in_stac.begin()+i);
    vector<int> right_in_stac(in_stac.begin() + i + 1, in_stac.end());
    vector<int> left_out_stac(out_stac.begin(), out_stac.begin() + i);
    vector<int> right_out_stac(out_stac.begin() + i, out_stac.end() - 1);
    for (int a = 0; a < left_in_stac.size();a++){
        if(find(left_in_stac.begin(),left_in_stac.end(),out_stac[a])==left_in_stac.end()){
            return false;
        }
    }
    return is_legal(left_in_stac, left_out_stac, 0, left_in_stac.size() - 1) && is_legal(right_in_stac, right_out_stac, 0, right_out_stac.size() - 1);
}
int main(){
    int n;
    cin >> n;
    vector<int> in_stac;
    vector<int> out_stac;
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        in_stac.push_back(temp);
    }
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        out_stac.push_back(temp);
    }
    cout << is_legal(in_stac, out_stac, 0, in_stac.size() - 1);
}
```

- 给定一个入栈序列，序列长度为N，请给出种出栈序列

```cpp
#include<iostream>
#include<stack>
#include<algorithm>
#include<vector>
using namespace std;
vector<int> path;

vector<vector<int>> result;
void dfs(int cur, vector<int>&arr, stack<int>&st)
{
    if(cur==arr.size()&&st.empty()){
            result.push_back(path);
        return;
    }

    if (cur < arr.size())
    {
        // 选择1: 将当前元素压入栈中
        st.push(arr[cur]);
        dfs(cur + 1, arr, st);
        st.pop(); // 撤销选择1
    }

    if (!st.empty())
    {
        // 选择2: 将栈顶元素出栈并加入路径
        path.push_back(st.top());
        int temp = st.top(); // 保存当前栈顶元素
        st.pop();
        dfs(cur, arr, st); // 不增加 cur，继续从当前元素出发
        st.push(temp);     // 恢复栈顶元素
        path.pop_back();   // 撤销选择2
    }
}
int main(){
    int n;
    cin >> n;
    vector<int> arr;
    for (int i = 0; i < n;i++){
        int temp;
        cin >> temp;
        arr.push_back(temp);
    }
    stack<int> st;
    dfs(0, arr,st);
    for (int i = 0; i < result.size();i++){
        for (int j = 0; j < result[i].size();j++){
            cout << result[i][j] << " ";
        }
        cout << endl;
    }
    
}
```



- 给定一个入栈序列，序列长度为N，请计算有多少种出栈序列



![Screenshot_2024-07-28-16-22-16-837_com.orion.notein](./algorithm.assets/Screenshot_2024-07-28-16-22-16-837_com.orion.notein-1724411809475-76-1724414108617-26.png)

最后一步涉及离散数学的知识

- 为什么栈不允许“读取内部元素”，只能在栈顶操作？

![image-20240728162408449](./algorithm.assets/image-20240728162408449-1724411809475-77-1724414108617-28.png)

栈是一种遵循“后进先出”（LIFO, Last In, First Out）原则的数据结构。它的设计目的是在数据管理过程中提供一种简单而有效的访问方式。这种设计背后的原因有几个关键点：

1. **数据访问的简化**：栈的结构使得数据的访问和管理变得非常简单和高效。由于只能从栈顶操作（即入栈和出栈），不需要考虑栈中其他元素的状态，这减少了复杂性和潜在的错误。

2. **数据完整性的保证**：栈的访问限制有助于保护数据的完整性。在一些应用场景中，特别是程序的函数调用过程中，栈用于管理局部变量和函数调用的返回地址。只能通过栈顶访问，防止其他函数或进程意外修改栈中间的数据，从而保障数据的安全性和一致性。

3. **栈的典型应用**：栈在许多计算机科学和编程领域有着广泛的应用。例如，程序的递归调用栈、表达式的解析和计算、浏览器的前进后退功能等。它们都依赖于栈的LIFO特性。允许随意访问栈中的元素可能会破坏这些应用的逻辑结构。

4. **效率问题**：如果允许在栈中随机访问元素，会导致数据结构的复杂度增加，同时降低操作的效率。栈的操作（入栈、出栈、查看栈顶元素）通常都是 O(1) 时间复杂度，而增加随机访问功能可能会带来更高的时间复杂度。

综上所述，栈的设计初衷和应用场景决定了它只允许在栈顶进行操作。这样不仅简化了数据管理，也保护了数据的完整性，并且提高了操作的效率。

## 栈的实现方式

- 顺序栈（Array-base Stack）
  - 使用向量实现，本质上是顺序表的简化版
    - 栈的大小
  - 关键是确定==哪一端==作为栈顶
  - 上溢、下溢

- 链式栈(Linked Stack)
  - 用单链表方式存储，其中指针的方向是从栈顶向下链接



==顺序栈的类定义==

- 上溢(Overflow)
  - 当栈中已经有maxsize个元素时，如果再做进栈运算，所产生的现象
- 下溢(Underflow)
  - 对空栈进行出栈运算时所产生的现象

```cpp
template<class T>class arrStack:public Stack<T>{
    private://栈的顺序存储
    	int maSize;//栈中最多存放的元素个数
    	int top;//栈顶位置，应小于mSize
    	T *st;//存放栈元素的数组
    public:
    	arrStack(int size){
            mSize=size;top=-1;st=new T[mSize];
        }
    	~arrStack(){delete []st;}
    	void clear(){top=-1;}//清空栈
};
bool arrStack<T>::push(const T item){
    if(top==mSize-1){//栈已满
        return false;
    }
    else{
        st[++top]=item;
        return true;
    }
}
bool arrStack<T>::pop(T &item){
    if(top==-1){
        cout<<"栈为空，不能进行出栈操作"<<endl;
        return false;
    }
    else{
        item=st[top--];
        return true;
    }
}
bool top(T & item){
    if(top==-1){
        cout<<"栈为空，不能读取栈顶元素"<<endl;
        return false;
    }
    else{
        item=st[top];
        return true;
    }
}
```



==链式栈的创建==

- 用单链表方式存储
- 指针方向从==栈顶向下==连接

如图：

![image-20240728194932531](./algorithm.assets/image-20240728194932531-1724411809475-78-1724414108617-27.png)

数据成员==top==是一个指向链式栈的首节点（栈顶）的指针，链表的结点类型采用上一章的==Link==模版。进栈操作`push`在链表头插入元素，出栈操作`pop`删除链头元素并释放空间。显而易见，`push`和`pop`的时间代价为`O(1)`

栈的链式实现

```cpp
	template<class T>
	class lnkStack:public Stack<T>{
        private://栈的链式存储
        	Link<T>* top;//指向栈顶的指针
        	int size;//存放元素的个数
        public://栈运算的链式实现
        	lnkStack(int defSize){//构造函数
                top=NULL;
                size=0;
            }
        	~lnkStack(){
                clear();
            }
        	void clear(){
                while(top!=NULL){
                    Link<T>*tmp=top;
                    top=top->next;
                    delete tmp;
                }//一步步清除节点
                size=0;
            }
        	bool push(const T item){	//入栈操作的顺序实现
                Link<T>* tmp=new Link<T>(item,top);
                top=tmp;
                size++;
                return true;
            }
        	bool pop(T& item){
                if(top==nullptr||size==0)return false;
                Link<T>* tmp=top;
                top=top->next;
                delete tmp;
                size--;
                return true;
            }
        	bool top(T & item){	//返回栈顶内容，但不弹出
            	if(size==0){
                    cout<<"栈为空，不能读取栈顶元素"<<endl;
                    return false;
                }
                item=top->data;
                return true;
                
            }
        	
    };
```

### 顺序栈和链式栈的比较

- 时间效率
  - 所有操作都只需常数时间
  - 顺序栈和链式栈在时间效率上难分伯仲
- 空间效率
  - 顺序栈须说明一个固定的长度
  - 链式栈的长度可变，但增加==结构性开销==（指的是指针）

- 实际应用中，顺序栈比链式栈用得更广泛







### 栈与递归的关系是什么

>#### 栈与递归的关系
>
>栈（Stack）和递归（Recursion）在数据结构与算法中有着密切的关系。以下是它们之间关系的详细讨论，以及为什么递归调用是栈的一个典型应用范例。
>
>##### 1. 栈的基本概念
>栈是一种后进先出（LIFO，Last In First Out）的数据结构。栈中的操作主要包括：
>- **压栈（Push）**：将元素添加到栈顶。
>- **弹栈（Pop）**：从栈顶移除元素。
>- **查看栈顶元素（Peek）**：获取栈顶元素但不移除它。
>
>##### 2. 递归的基本概念
>递归是一种在函数内部调用自身的编程技巧。一个递归函数通常包含两个部分：
>- **基例（Base Case）**：定义了递归终止的条件。
>- **递归部分（Recursive Case）**：函数调用自身来解决更小的子问题。
>
>##### 3. 递归与栈的关系
>每次函数调用，系统会在内存中为该函数分配一个栈帧（Stack Frame），其中包含了函数的局部变量、参数、返回地址等信息。当一个递归函数调用自身时，会生成新的栈帧并压入调用栈中，直到达到基例。递归调用的返回过程就是栈帧从调用栈中依次弹出的过程。
>
>###### 具体过程
>1. **递归调用阶段**：
>   - 每次递归调用，当前函数的执行被挂起，当前状态被保存到栈中。
>   - 新的栈帧被创建并压入调用栈，处理递归调用的子问题。
>
>2. **递归返回阶段**：
>   - 当递归基例条件满足时，递归开始返回。
>   - 栈帧从调用栈中弹出，恢复到上一个函数的执行状态。
>
>##### 4. 为什么递归是栈的一个应用范例？
>递归函数在执行时，系统自动使用调用栈来管理函数调用。每个函数调用都会导致一个新的栈帧被压入栈中，递归的深度越深，调用栈中的栈帧也越多。因此，递归算法的实现与栈的操作天然对应。通过理解递归调用栈的工作机制，可以更好地掌握递归算法的执行过程。
>
>##### 5. 示例代码
>下面是一个简单的递归函数和它的非递归（使用显式栈）实现，以求解阶乘为例：
>
>###### 递归实现：
>```cpp
>int factorial(int n) {
>    if (n == 0) return 1; // 基例
>    return n * factorial(n - 1); // 递归调用
>}
>```
>
>###### 非递归实现（使用栈）：
>```cpp
>#include <stack>
>int factorial(int n) {
>    std::stack<int> s;
>    int result = 1;
>    while (n > 0) {
>        s.push(n);
>        n--;
>    }
>    while (!s.empty()) {
>        result *= s.top();
>        s.pop();
>    }
>    return result;
>}
>```
>
>通过上面的代码可以看到，递归实现依赖于系统的调用栈，而非递归实现则通过显式的栈来管理递归过程。两者本质上是等价的，只是处理方式不同。
>
>##### 总结
>递归和栈是密切相关的概念，递归调用天然地依赖于调用栈的管理。因此，递归是栈的一个经典应用范例，通过理解递归调用的栈机制，可以更好地掌握递归算法的执行过程。
>
>

# 栈的应用

## 计算表达式求值

- 表达式的递归定义
  - 基本符号集：{0,1，……,9,+,-,*,/,(,)}
  - 语法成分集：{<表达式>,<项>，<因子>,<常数>,<数字>}
  - 语法公式集：语法公式又称为产生式规则，用于定义语法成分。为了简便，在不影响通用性的前提下，下面给出的表达式的语法公式进行了简化处理：
    - <表达式>::=<项>+<项>|<项>-<项>|<项>
    - <项>       ::=<因子>*<因子>|<因子>/<因子>|<因子>
    - <因子>   ::=<常数>|(<表达式>)
    - <常数>   ::=<数字>|<数字><常数>
    - <数字>   ::=0~9
- 中缀表达式：23+（34*45）/（5+6+7）
  - ![image-20240814111409063](./algorithm.assets/image-20240814111409063-1724411809475-79-1724414108617-29.png)

- 后缀表达式：23 34 45 * 5 6 + 7 + / +

![5c7f4b2c63241fe2042adaf77eef8e4](./algorithm.assets/5c7f4b2c63241fe2042adaf77eef8e4-1724411809475-80-1724414108617-30.jpg)

### 中缀表达式到后缀表达式的转换

==将中缀表达式转换成等价的后缀表达式的关键在于如何恰当地去除中缀表达式的括号，然后再必要时按先乘除后加减的优先规则调换运算符的先后顺序，在去括号的过程中用栈来存储有关的元素==

*基本思路*：从左到右顺序扫描中缀表达式，用栈来存放表达式中的操作数，开括号以及在这个开括号后面的其他暂时不能确定计算次序的内容

中缀表达式以字符串InfixExp表示，转换后的后缀表达式用字符串PostfixExp来表示，则该转换算法的输入即为InfixExp，输出便为PostfixExp。

==实现步骤==：

- 当输入的是操作数时，直接输出到后缀表达式PostfixExp序列中
- 当遇到开括号时，将其入栈
- 当输入遇到闭括号时，先判断栈是否为空，若为空，则出现异常情况，清栈退出。若费控，则把栈中的元素依次弹出，直到遇到第一个开括号为止，将弹出的元素输出到后缀序列。注意不要把括号放到后缀序列内
- 当输入为运算符时：
  - 循环，当==栈非空&&栈顶不是开括号&&栈顶元素的优先级大于等于要输入运算符的优先级==时，反复操作将栈顶元素弹出，放到后缀表达式序列
  - 将输入的运算符压入栈中

- 最后，扫描完毕时，若栈内仍有元素，则将其全部依次弹出，放在后缀表达式序列尾部

==代码实现（纯手敲,，累死版）==

```cpp
#include<iostream>
#include<stack>
#include<cmath>
#include<string>
using namespace std;
bool compare_the_levels_of_priorities(char cur,char stcur){
    if(stcur=='+'||stcur=='-'){
        if(cur=='*'||cur=='/'){
            return false;
        }
    }
    return true;
}
bool isNumber(char c){
    return ((c >= '0' && c <= '9') || c == '.');
}
bool isOperator(char c){
    return c == '+' || c == '-' || c == '*' || c == '/';
}
string transform(string InfixExp){
    string PostfixExp;
    stack<char> st;
    string num;
    char cur;
    for (int i = 0; i < InfixExp.size();i++){
        cur = InfixExp[i];
        if(isNumber(cur)){
            num.push_back(cur);
            if (i == InfixExp.size() - 1 || !isNumber(InfixExp[i + 1]))
            {
                PostfixExp.append(num + " ");
                num.clear();
           }
        }
        else if(cur=='('){
            st.push(cur);
        }
        else if(cur==')'){
            if(st.empty()){
                cout << "输入有问题" << endl;
            }
            else{
                char stcur = st.top();
                st.pop();
                while(stcur!='('){
                    PostfixExp.push_back(stcur);
                    PostfixExp.push_back(' ');
                    stcur = st.top();
                    st.pop();
                }
            }
        }
        else if(isOperator(cur)){
            
                while (!st.empty() && st.top() != '(' && compare_the_levels_of_priorities(cur, st.top())){
                    PostfixExp.push_back(st.top());
                    PostfixExp.push_back(' ');
                    st.pop();
                }
                st.push(cur);
        }
        
    }
    while(!st.empty()){
        PostfixExp.push_back(st.top());
        PostfixExp.push_back(' ');
        st.pop();
    }
    return PostfixExp;
}
int main(){
    string InfixExp;
    cin >> InfixExp;
    string PostfixExp = transform(InfixExp);
    cout << PostfixExp;
    return 0;
}
```





### 后缀表达式求值

计算过程：

- 如果遇到一个操作数，则压入栈中。
- 如果遇到一个运算符，就从栈中弹出两个操作数，按照运算符对这两个操作数进行相应的运算，然后将计算结果压入栈中。

如此继续，直到遇到符号“=”，此时栈顶的值就是输入表达式的值。例如，后缀表达式

 23 34 45 * 5 6 + 7 + / +

![image-20240814224919876](./algorithm.assets/image-20240814224919876-1724411809475-81-1724414108617-31.png)

==代码（纯手敲）==

```cpp
#include <iostream>
#include <string>
#include <cmath>
#include <stack>
using namespace std;
bool isNumber(char c)
{
    return ((c >= '0' && c <= '9') || c == '.');
}
bool isOperator(char c)
{
    return c == '+' || c == '-' || c == '*' || c == '/';
}
int operator_result(string PostfixExp)
{
    string num;

    stack<double> st;
    char cur;
    for (int i = 0; i < PostfixExp.size(); i++)
    {
        cur = PostfixExp[i];
        if (isNumber(cur))
        {
            num.push_back(cur);

            if (i == PostfixExp.size() - 1 || !isNumber(PostfixExp[i + 1]))
            {
                st.push(stod(num));              
                num.clear();
            }
        }
        else if (isOperator(cur))
        {
            double result = 0;
            double num1 = st.top();
            st.pop();
            double num2 = st.top();
            st.pop();
            switch (cur)
            {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num2 - num1;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                result = num2 / num1;
                break;
            }
            st.push(result);
           
        }
    }
    return st.top();
}
int main()
{
    string PostfixExp;
    getline(cin,PostfixExp);
 
    cout << operator_result(PostfixExp) << endl;
}
```

==抽象类实现==



# 栈与递归

## 递归定义

一个递归由两部分组成：其一为==递归基础==，也称递归出口，是递归定义的最基本情况，其二为==递归规则==，确定了由简单情况构筑复杂情况需要构筑复杂情况需遵循的规则。

## 递归函数的实现

大多数程序设计语言运行环境所提供的函数调用机制是底层的编译栈支持的。编译栈中的“运行时环境”指的是目标计算机上用来管理存储器并保存执行过程所需信息的寄存器及存储器的结构。

==静态分配==：在非递归调用下，数据区的分配可以在程序运行前进行，直到整个程序运行结束再释放。

==递归调用==：被调函数的局部变量不能静态分配到某些固定单元，而必须每调用一次就分配一次，以存放当前所使用的数据，当返回时随机释放。这种只有在执行调用时才能进行的存储分配成为“动态分配”，此时需要在内存中开辟一个称为==运行栈==的足够大的动态区。

### 递归函数的执行

递归函数在每次调用时会生成一个新的函数实例并压入栈中。栈保存了函数的参数和局部变量。执行过程如下：

- 调用递归函数。
- 将当前状态压栈。
- 函数进行下一步递归调用。
- 当到达基准条件时，递归停止。
- 逐层从栈中弹出函数实例，恢复之前的执行状态，直至最外层的函数返回结果。

==对函数调用栈的解释==

>函数调用栈（Call Stack）是程序执行过程中管理函数调用与返回的关键机制。它的作用是追踪当前正在执行的函数以及这些函数的调用者，确保函数在执行完毕后能够正确返回调用它的地方。
>
>### 函数调用栈的基本原理
>
>1. **栈的结构**：
>   - 调用栈是一种后进先出的数据结构（LIFO），即最后压入栈的数据最先弹出。函数调用栈用于保存当前函数执行的环境信息（如局部变量、参数、返回地址等）。
>   - 每当一个函数被调用时，都会在调用栈中创建一个新的栈帧（Stack Frame），栈帧存储该函数的执行状态。
>   
>2. **栈帧（Stack Frame）**：
>     栈帧是调用栈中每个函数调用的记录，包含以下信息：
>   - **返回地址**：函数执行完毕后需要返回的地址。
>   - **函数参数**：当前调用传递的参数。
>   - **局部变量**：函数内定义的局部变量。
>   - **保存的寄存器**：CPU寄存器状态，以便函数返回时能够恢复。
>   
>   当函数返回时，该栈帧会从调用栈中弹出，并将控制权返回给调用者。
>
>### 函数调用栈的执行过程
>
>假设有两个函数 `A` 和 `B`，且 `A` 调用了 `B`，则函数调用栈的执行过程如下：
>
>1. **进入函数 A**：
>   - 函数 `A` 被调用时，栈中为 `A` 创建栈帧。
>   - 栈帧保存了 `A` 的局部变量、函数参数以及返回地址（即`A`完成执行后应该返回的位置）。
>
>2. **函数 A 调用函数 B**：
>   - 当 `A` 调用 `B` 时，栈中为 `B` 创建新的栈帧。
>   - `B` 的栈帧保存了 `B` 的参数、局部变量以及返回到 `A` 的地址。
>   - `A` 的栈帧依然保持在栈中，等待 `B` 执行完毕后恢复。
>
>3. **执行函数 B**：
>   - 在函数 `B` 的栈帧中，程序执行 `B` 的指令。
>   - 函数 `B` 完成后，其返回地址将指向调用它的函数 `A`，并从调用栈中弹出 `B` 的栈帧。
>
>4. **返回到函数 A**：
>   - 程序跳回 `A` 函数的返回地址。
>   - `A` 的栈帧被恢复，执行继续。
>
>5. **退出函数 A**：
>   - 当 `A` 完成执行后，其栈帧从调用栈中弹出。
>   - 控制权返回到最初调用 `A` 的位置。
>
>### 函数调用栈的优点
>
>- **管理函数调用**：调用栈自动管理函数调用的顺序，确保函数在调用后能够正确返回到调用点。
>- **支持递归调用**：递归调用时，每次递归调用都会创建新的栈帧，栈帧中保存各自的局部状态，保证了每次递归调用的独立性。
>
>### 函数调用栈的限制
>
>1. **栈空间有限**：调用栈的空间是有限的，通常由操作系统分配固定大小的内存。当递归深度过大或函数嵌套过深时，可能导致栈空间耗尽，发生栈溢出错误（Stack Overflow）。
>2. **调用开销**：每次函数调用都伴随着栈帧的创建和销毁，这会引入一些额外的开销，尤其是在递归调用较多时，性能可能受影响。
>
>### 递归函数的开销
>
>- 每次函数调用需要创建栈帧
>- 空间开销
>  - 实际中的栈帧可能很大（包含其它信息）
>  - 可能导致栈溢出，造成安全漏洞
>- 时间开销
>  - 栈操作
>  - 函数调用指令
>
>### 递归与调用栈
>
>在递归调用中，每个递归调用都会在栈中生成一个新的栈帧，直到达到基准条件开始返回。递归的结束会按调用顺序逐层从栈中弹出函数实例。由于递归会占用较多的栈空间，如果递归深度过大，容易导致栈溢出。
>
>### 总结
>
>函数调用栈是确保函数调用正确进行、状态恢复的重要机制。它自动管理函数的调用与返回、局部变量和参数的保存与恢复。但在处理递归时，需要注意栈的深度以避免溢出。
>
>

==绘图解释：==

​	![image-20240821083958353](./algorithm.assets/image-20240821083958353-1724411809475-82-1724414108617-32.png)

![image-20240821084014027](./algorithm.assets/image-20240821084014027-1724411809475-83-1724414108617-33.png)

![image-20240821084036419](./algorithm.assets/image-20240821084036419-1724411809475-84-1724414108617-34.png)

![image-20240821084047094](./algorithm.assets/image-20240821084047094-1724411809475-85-1724414108617-35.png)

![image-20240821084059931](./algorithm.assets/image-20240821084059931-1724411809476-86-1724414108617-36.png)

![image-20240821084109296](./algorithm.assets/image-20240821084109296-1724411809476-87-1724414108617-37.png)

![image-20240821084118290](./algorithm.assets/image-20240821084118290-1724411809476-88-1724414108617-38.png)

![image-20240821084127336](./algorithm.assets/image-20240821084127336-1724411809476-89-1724414108617-39.png)

![image-20240821084139984](./algorithm.assets/image-20240821084139984-1724411809476-90-1724414108617-40.png)

## 递归转为非递归

- 递归函数转非递归：减少开销

### 递归函数转非递归：尾递归

- 一类特殊的递归函数：尾递归
- 尾递归：函数==仅有一次==自身调用，且该调用是函数退出前的==最后一个==操作

==尾递归的解释==

>尾递归其实也是调用自身的一种方式，但它的特殊性在于函数的递归调用发生在**函数的最后一步**，而没有任何额外的计算或操作在递归调用之后。因此，尾递归可以被优化为**迭代**，从而不再需要维护多个栈帧。
>
>### 尾递归的定义
>
>**尾递归**指的是函数在返回结果之前唯一的操作是调用自身，递归调用发生在函数的**末尾**，且递归调用的结果直接作为函数的返回值。
>
>### 尾递归与普通递归的区别
>
>1. **普通递归**：
>   
>   - 普通递归的调用过程中，函数在调用自身后，通常会在返回结果之前进行一些额外的操作。
>   - 由于函数在递归调用后还有未完成的操作，每个递归调用都需要保留在栈中，直到所有递归调用完成，栈帧才能依次弹出。
>   
>   例如，计算阶乘的普通递归：
>   ```cpp
>   int factorial(int n) {
>       if (n == 1) {
>           return 1;
>       }
>       return n * factorial(n - 1);  // 递归调用之后还有乘法运算
>   }
>   ```
>   
>2. **尾递归**：
>   - 在尾递归中，函数调用自身的结果不再参与其他计算，而是直接返回。
>   - 因为递归调用是函数的最后一步，所以在许多编程语言和编译器中，可以进行优化，即复用当前的栈帧而不必创建新的栈帧。这样可以避免栈溢出。
>
>   尾递归形式的阶乘计算：
>   ```cpp
>   int factorial_tail(int n, int acc = 1) {
>       if (n == 1) {
>           return acc;
>       }
>       return factorial_tail(n - 1, n * acc);  // 尾递归，递归调用直接返回
>   }
>   ```
>
>### 尾递归优化
>
>当编译器或解释器检测到尾递归时，它会进行**尾调用优化**（Tail Call Optimization, TCO）。在这种情况下，当前栈帧不会在递归调用后保留，而是直接复用栈帧。这使得尾递归可以像循环一样有效运行，不会因为递归深度过大而耗尽栈空间。
>
>因此，**尾递归**虽然也是调用自身，但由于它的优化特性，可以在不增加栈空间的情况下高效运行，类似于迭代。
>
>### 为什么尾递归有时不被称为"调用自身"
>
>尽管尾递归本质上仍然是调用自身，部分编程社区或文档中不将其单独称为“调用自身”，主要是因为尾递归的实现方式和普通递归有较大区别：
>
>- 普通递归：每次调用自身都会增加栈帧，栈帧保存了递归的上下文信息。
>- 尾递归：由于尾调用优化的存在，递归调用并不会增加新的栈帧，因此其表现更像循环。
>
>因此，在一些编程语言中，尾递归不再被视为传统意义上的递归，而更接近于一种高效的循环调用。

- 尾递归可以很容易转化成非递归形式

  - 尾递归的本质：将单词计算的结果缓存起来，传递给下次调用，相当于自动累积
  - 转化非递归：通过循环迭代，每次保存累计结果

- 转化之后：没有栈开销，没有函数调用开销

  - 递归调用：线性空间
  - 非递归循环：常数空间

  >当递归转换为尾递归时，经过**尾调用优化（Tail Call Optimization, TCO）**，可以避免函数调用的开销。这是因为尾递归允许编译器或解释器通过优化机制来减少函数调用的成本，具体过程如下：
  >
  >### 函数调用的开销
  >
  >在普通递归中，每次递归调用都会涉及到以下几个步骤，这些步骤引入了额外的开销：
  >1. **保存当前函数的状态**：包括函数的局部变量、参数、返回地址等，保存在栈帧中。
  >2. **创建新的栈帧**：为递归调用创建新的函数执行环境，并将其压入调用栈。
  >3. **恢复执行状态**：当递归返回时，依次从栈中弹出栈帧，恢复上一个调用的执行状态，继续进行剩余操作。
  >
  >这些操作消耗了CPU资源并占用了内存的栈空间。对于深度递归，开销会随着递归深度的增加而迅速累积，甚至可能导致**栈溢出**。
  >
  >### 尾递归与尾调用优化的原理
  >
  >尾递归中的递归调用发生在函数的最后一步，意味着在递归调用之后，函数无需进行任何额外操作。这使得编译器可以优化递归调用，省略不必要的栈帧。具体优化步骤如下：
  >
  >1. **不保存当前栈帧**：由于递归调用是函数的最后一步，不再需要保留当前函数的执行上下文。因此，编译器可以直接复用当前栈帧，而不是创建新的栈帧。
  >   
  >2. **复用栈帧**：在尾递归优化中，递归调用的栈帧会替代当前的栈帧。这意味着每次递归调用不会增加新的栈帧，从而减少了栈空间的使用。
  >
  >3. **无堆栈增长**：由于栈帧不会累积，递归调用的开销大大降低。尾递归优化的表现更像一个循环，随着每次递归调用，栈帧保持恒定大小，不会像普通递归那样逐步增加。
  >
  >### 举例说明
  >
  >考虑以下尾递归函数：
  >
  >```cpp
  >int factorial_tail(int n, int acc = 1) {
  >    if (n == 1) {
  >        return acc;
  >    }
  >    return factorial_tail(n - 1, n * acc);  // 尾递归
  >}
  >```
  >
  >对于编译器来说，这个函数在调用 `factorial_tail` 时无需创建新的栈帧，因为它的唯一操作是直接返回递归调用的结果。因此，编译器可以直接复用当前的栈帧，省去函数调用的开销。
  >
  >### 为什么尾递归没有函数调用开销？
  >
  >由于编译器或解释器的尾调用优化，尾递归调用中的栈帧不会堆积，递归调用过程中的上下文切换、栈帧管理等操作也被简化。所有的递归调用都在同一个栈帧中完成，因此：
  >- **没有额外的栈空间消耗**：栈帧不再堆积，递归深度不会影响内存使用。
  >- **没有额外的函数调用开销**：每次递归调用仅仅复用了当前栈帧，而不是创建新的栈帧。
  >
  >### 尾递归优化的前提
  >
  >需要注意的是，尾递归优化并非所有语言或编译器都支持。对于不支持尾递归优化的环境，即使函数满足尾递归条件，依然会产生函数调用开销。
  >
  >### 总结
  >
  >尾递归之所以可以没有函数调用开销，是因为通过尾调用优化，递归调用可以在同一栈帧中完成，从而消除了创建和管理额外栈帧的需要。这使得尾递归在执行效率上类似于循环，没有普通递归那样的栈空间和函数调用开销。



#### 通用的递归到非递归的转化

- 思想：通过显式模拟函数调用过程
  - 特别是模拟调用栈的操作
- 好处：适用于==所有==递归函数（机械转换）
  - 空间：减少冗余存储
  - 时间：减少冗余操作（特别是函数跳转）

==例子==：

递归版本：

```cpp

long fact(long n){
    if(n<=1)
        return 1;
    else 
        return n*fact(n-1);
}
```



非递归版本：

```cpp
long fact_nr(long n){
    stack<long>s;
    long ret=1;
    while(n>0)
        s.push(n--);
    while(!s.empty()){
        long top=s.top();
        ret*=top;
        s.pop();
    }
}
```



#### 问题实例

- [简化的0-1背包问题]

​	我们有n件物品，物品i的重量为`w[i]`。如果限定每种物品：要么完全放进背包，要么不放进背包，即物品是不可分割的。

​	问：能否从这n件物品中选择若干件放入背包，使其重量之和恰好为s

==动态规划（题外话）==

```cpp
#include<iostream>
#include<stack>
#include<vector>
using namespace std;
int main(){
    int n;
    cin >> n;
    int s;
    cin >> s;
    vector<int> stuff;
    for (int i = 0; i < n;i++){
        int h;
        cin >> h;
        stuff.push_back(h);
    }
    vector<int> dp(s+1,0);
    for (int i = 0; i < n;i++){
        for (int j = s; j >= stuff[i];j--){
            dp[j] = max(dp[j], dp[j - stuff[i]] + stuff[i]);
        }
    }
    cout << ((dp[s] == s) ? "true":"false") << endl;
}
```



==递归==



递归关系：

​	

- `knap(s,n)=`

  - `true`  if s=0
  - `false` if s<0 or (s>0 and n<1)
  - $$knap(s-w_{n-1},n-1)or  knap(s,n-1)$$

  ```cpp
  #include<iostream>
  #include<stack>
  #include<vector>
  using namespace std;
  bool knap(int s, int n,vector<int> w)
  {
      if(s==0)
          return true;
      else if(s<0||(s>0&&n<1))
          return false;
      else if(knap(s-w[n-1],n-1,w)){
          cout << w[n - 1] << " ";
          return true;
      }
      else{
          bool tmp = knap(s, n - 1,w);
          return tmp;
      }
  }
  int main(){
      int n;
      cin >> n;
      int s;
      cin >> s;
      vector<int> w;
      for (int i = 0; i < n;i++){
          int h;
          cin >> h;
          w.push_back(h);
      }
      knap(s, n,w);
  }
  ```

  

==递归转换为非递归==

原递归式子

```cpp
bool knap(int s,int n){
    if(s==0)return true;
    else if((s<0)||(s>0&&n<1))
        return false;
    else if(knap(s-w[n-1],n-1)){
        cout<<w[n-1]<<" ";
        return true;
    }
    else{
        bool tmp=knap(s,n-1);
        return tmp;
    }
}
```



- 步骤一：定义调用栈帧

  ```cpp
  struct Elem{
      int s;
      int n;
      int rd;
      Elem(int s,int n,int rd):s(s),n(n),rd(rd){}
     
  };
  ```

- 步骤二:将原问题压入栈

  ```cpp
  bool knap(int s,int n){
      stack<Elem>st;//创建栈
      Elem x(s,n,0);//原问题栈帧
      st.push(x);//入栈
      bool ret;//最近一次调用结果
      //more
  }
  ```

- 步骤三：程序分析

  ![image-20240821105012251](./algorithm.assets/image-20240821105012251-1724411809476-91-1724414108617-41.png)

![image-20240821105520771](./algorithm.assets/image-20240821105520771-1724411809476-92-1724414108617-42.png)

- 步骤四：划分标签、翻译

  ![image-20240821110438284](./algorithm.assets/image-20240821110438284-1724411809476-93-1724414108617-43.png)

![image-20240821110458148](./algorithm.assets/image-20240821110458148-1724411809476-94-1724414108617-44.png)

![image-20240821110508887](./algorithm.assets/image-20240821110508887-1724411809476-95-1724414108617-45.png)

![image-20240821110519729](./algorithm.assets/image-20240821110519729-1724411809476-96-1724414108617-46.png)

![image-20240821110531568](./algorithm.assets/image-20240821110531568-1724411809476-97-1724414108617-47.png)

小结：t次递归调用，添加t+2个标签

- 步骤五：用`goto`实现递归调用

  ```cpp
  bool knap(int s ,int n){
      stack<Elem>st;
      Elem x(s,n,0);
      st.push(x);
      bool ret;
      L0://第一个标签
  	s=st.top().s;
      n=st.top().n;
      if(s==0){
          ret=true;
          TODO return ;//递归出口
      }
      if((s<0)||(s>0&&n<1)){
          ret=false;
          TODO return ;//递归出口
      }
      //第一次递归调用
      st.push(Elem(s-w[n-1],n-1,1));goto L0;
      L1://第二个标签
      s=st.top().s;
      n=st.top().n;
      if(ret){
          cout<<w[n-1]<<" ";
          ret=true;
          TODO return;//递归出口
      }
      else{
          //第二次递归调用
          st.push(Elem(s,n-1,2));goto L0;
           L2://第三个标签
      	TODO return ;//递归出口
      }
     L3:TODO://递归退出，决定返回地址
      
      
  }
  ```

  ==小结==：t次递归调用，添加t+2个标签

- 步骤六：处理`return`语句(所有`return` 都 `goto` 到最后一个标签)

  ```cpp
  bool knap(int s ,int n){
      stack<Elem>st;
      Elem x(s,n,0);
      st.push(x);
      bool ret;
      L0://第一个标签
  	s=st.top().s;
      n=st.top().n;
      if(s==0){
          ret=true;
          goto L3 ;//递归出口
      }
      if((s<0)||(s>0&&n<1)){
          ret=false;
          goto L3 ;//递归出口
      }
      //第一次递归调用
      st.push(Elem(s-w[n-1],n-1,1));goto L0;
      L1://第二个标签
      s=st.top().s;
      n=st.top().n;
      if(ret){
          cout<<w[n-1]<<" ";
          ret=true;
          goto L3;//递归出口
      }
      else{
          //第二次递归调用
          st.push(Elem(s,n-1,2));goto L0;
           L2://第三个标签
      	goto L3 ;//递归出口
      }
     L3:TODO://递归退出，决定返回地址
      
      
  }
  ```

  

- 步骤七：实现递归退出

  ```cpp
  bool knap(int s ,int n){
      stack<Elem>st;
      Elem x(s,n,0);
      st.push(x);
      bool ret;
      L0://第一个标签
  	s=st.top().s;
      n=st.top().n;
      if(s==0){
          ret=true;
          goto L3 ;//递归出口
      }
      if((s<0)||(s>0&&n<1)){
          ret=false;
          goto L3 ;//递归出口
      }
      //第一次递归调用
      st.push(Elem(s-w[n-1],n-1,1));goto L0;
      L1://第二个标签
      s=st.top().s;
      n=st.top().n;
      if(ret){
          cout<<w[n-1]<<" ";
          ret=true;
          goto L3;//递归出口
      }
      else{
          //第二次递归调用
          st.push(Elem(s,n-1,2));goto L0;
           L2://第三个标签
      	goto L3 ;//递归出口
      }
     L3:
      switch((x=st.top().rd)){
          case 0:st.pop();return ret;
          case 1:st.pop();goto L1;
          case 2:st.pop();goto L2;
          default:assert(false);
      }//递归退出，决定返回地址
      
      
  }
  
  ```

  ##### 具体实例

  假设我们有3个物品，它们的重量分别为`w[0] = 10`, `w[1] = 20`, `w[2] = 30`。我们想确定是否能从这些物品中选择一些，使它们的总重量恰好为`s = 50`。

  ##### 递归程序的函数调用栈情况

  1. `knap(50, 3)`：检查总重量为50，物品数量为3。
  2. `knap(40, 2)`：选择物品3（重量30），检查剩余重量为20，物品数量为2。
  3. `knap(20, 1)`：选择物品2（重量20），检查剩余重量为0，物品数量为1。
  4. `knap(0, 0)`：达到基本情况，返回true。
  5. 从`knap(20, 1)`返回true，因为它找到了一个解。
  6. `knap(40, 2)`打印物品3的重量（30），然后返回true。
  7. `knap(50, 3)`从`knap(40, 2)`返回true，表示找到了一个解。

  ##### 函数调用栈示例

  ```
  复制knap(50, 3)
    -> knap(40, 2) [物品3被选中]
      -> knap(20, 1) [物品2被选中]
        -> knap(0, 0) [基本情况]
      返回true
      打印物品3的重量
    返回true
  返回true
  ```

```cpp
#include<iostream>
#include<stack>
#include<vector>
#include<cassert>
using namespace std;
vector<int> w;
struct Elem
{
    int s;
    int n;
    int rd;
    Elem(int s, int n, int rd) : s(s), n(n), rd(rd) {}
};
bool knap(int s, int n)
{
    w.push_back(10);
    w.push_back(20);
    w.push_back(30);
    stack<Elem> st;
    Elem x(s, n, 0);
    st.push(x);
    bool ret;
L0: // 第一个标签
    s = st.top().s;
    n = st.top().n;
    if (s == 0)
    {
        ret = true;
        goto L3; // 递归出口
    }
    if ((s < 0) || (s > 0 && n < 1))
    {
        ret = false;
        goto L3; // 递归出口
    }
    // 第一次递归调用
    st.push(Elem(s - w[n - 1], n - 1, 1));
    goto L0;
L1: // 第二个标签
    s = st.top().s;
    n = st.top().n;
    if (ret)
    {
        cout << w[n - 1] << " ";
        ret = true;
        goto L3; // 递归出口
    }
    else
    {
        // 第二次递归调用
        st.push(Elem(s, n - 1, 2));
        goto L0;
    L2:          // 第三个标签
        goto L3; // 递归出口
    }
L3:
    switch ((x = st.top()).rd)
    {
    case 0:
        st.pop();
        return ret;
    case 1:
        st.pop();
        goto L1;
    case 2:
        st.pop();
        goto L2;
    default:
        assert(false);
    } // 递归退出，决定返回地址
}


int main(){

    knap(50, 3);
}
```

#### 总结

- 步骤一：定义栈帧，建立调用栈
- 步骤二：在栈中压入原始问题的帧(rd=0)
- 步骤三：根据递归调用数`t`，将程序`t+1`个区域（t+1个递归出口）
- 步骤四：创建`(t+2)`个标签，逐区域翻译（除`return`语句、递归调用）
  - `t+2`个标签为`t+1`个区域的边界

- 步骤五：用`goto`实现递归调用
  - 形式"`push stack;goto label 0`",第`i`个调用`rd=i`
- 步骤六：用`goto`实现`return`语句
  - 将所有"`return`"替换为“`goto label(t+1)`”
- 步骤七：在标签`t+1`后添加递归出口
  - 使用"switch"语句，根据栈顶的`rd`值判断继续执行的标签

- 可选：代码优化

#### 思考题

- 问题：将前面提到的阶乘函数使用机械步骤转化为非递归形式

```cpp
long fact(long n){
    if(n<=1)return 1;//递归出口1
    int tmp1=fact(n-1);//调用自身1次
    int tmp2=tmp1*n;
    return tmp2;//递归出口2
}
```



栈帧：

```cpp
struct Elem(){
    int n;
    int rd;
    Elem(int n,int rd):n(n),rd(rd){}
};
```

非递归形式：

```cpp
int fact(int n)
{
    stack<Elem> st;
    st.push(Elem(n, 0));
    int ret;
L0:
    if (st.top().n <= 1){
        ret = 1;
    goto L2;}
    st.push(Elem(st.top().n - 1, 1));
    goto L0;
L1:
    ret = st.top().n * ret;
    goto L2;
L2:
    switch(st.top().rd)
    {
    case 0:
        st.pop();
        return ret;
    case 1:
        st.pop();
        goto L1;
    }
}
```

完整形式：


```cpp
#include<iostream>
#include<stack>
#include<vector>
#include<cassert>
using namespace std;
struct Elem
{
    int n;
    int rd;
    Elem(int n, int rd) : n(n), rd(rd) {}
};
int fact(int n)
{
    stack<Elem> st;
    st.push(Elem(n, 0));
    int ret;
L0:
    if (st.top().n <= 1){
        ret = 1;
    goto L2;}
    st.push(Elem(st.top().n - 1, 1));
    goto L0;
L1:
    ret = st.top().n * ret;
    goto L2;
L2:
    switch(st.top().rd)
    {
    case 0:
        st.pop();
        return ret;
    case 1:
        st.pop();
        goto L1;
    }
}
int main(){

    cout << fact(4) << endl;
}
```



# 队列

==注意==：有许多定义与C++不同，先按照课本上的做笔记

- 先进先出（first in first out ）
  - 限制访问点的线性表
  - 所有插入在表的一端进行，所有删除都在表的另一端进行
- 主要元素
  - 队头（front）
  - 队尾（back）

## 队列的抽象数据类型

```cpp
template<class T>
	class Queue{
        public:
        	void clear();//变为空队列
        	bool enQueue(const T item);//将item插入队尾，成功则返回真，否则返回假
        	bool deQueue(T & item);//返回队头元素并将其从队列中删除，成功则返回真
        	bool getFront(T& item);//返回队头元素，但不删除，成功则返回真
        	bool isEmpty();//返回真，若队列已空
        	bool isFull();//返回真，若队列已满
    };
```

## 队列的实现方式

- 顺序队列
  - 关键是如何防止假溢出
- 链式队列
  - 用单链表方式存储，队列中每个元素对应链表中的一个结点

### 顺序队列

- 用向量存储队列元素，用两个变量分别指向队列的前段（front）和尾端（rear）

  - *front*:指向当前*待出队*的元素位置（地址）
  - *rear*：指向当前*待入队*的元素位置（地址）

  

![image-20240822132432039](./algorithm.assets/image-20240822132432039-1724411809476-98-1724414108617-48.png)



队列的溢出

- 上溢
  - 当队列满时，再做进队操作，所出现的现象
- 下溢
  - 当队列空时，再做删除操作，所出现的现象
- 假溢出
  - 当rear=mSize-1时，再作插入运算就会产生溢出，如果这时队列的前段还有许多空位置，这时队列的前端还有许多空位置，这种现象叫做假溢出

### 队列的类定义

```cpp
class arrQueue:public Queue<T>{
    private:
    int mSize;//存放队列的数组大小
    int front;//表示队头所在位置的下标
    int rear;//表示待入队元素所在位置的下标
    T* qu;//存放类型为T的队列元素的数组
    public:
    	arrQueue(int size){//创建队列的实例
            mSize=size+1;//浪费一个存储空间，以区别队列空和队列满
            qu=new T[mSize];
            front=rear=0;
        }
    	~arrQueue(){
            delete[]qu;//消除该实例，并释放其空间
        }
};
bool arrQueue<T>::enQueue(const T item){
    // item入队，插入队尾
    if(((rear+1)%mSize)==front){
        cout<<"队列已满，溢出"<<endl;
        return false;
    }
    qu[rear]=item;
    rear=(rear+1)%mSize;//循环后继
    return true;
}
bool arrQueue<T>::deQueue(T& item){//返回队头元素并从队列中删除
    if(front==rear){
        cout<<"队列为空"<<endl;
        return false;
    }
    item=qu[front];
    front=(front+1)%mSize;
    return true;
}
```

## 链式队列

- 单链表队列
- 链接指针的方向是从队列的前端想尾端链接



![image-20240822135823322](./algorithm.assets/image-20240822135823322-1724411809476-99-1724414108617-49.png)



### 链式队列的类定义

```cpp
template<class T>
    class lnkQueue:public Queue<T>{
        private:
        	int size;//队列中当前元素的个数
        	Link<T>* front;//表示队头的指针
        	Link<T>* rear;//表示队尾的指针
        public:
        	lnkQueue(int size);//创建队列的实例
        	~lnkQueue();//消除该实例，并释放空间
    }
bool enQueue(const T item){
    //item入队，插入队尾
    if(rear==NULL){
        //空队列
        front=rear=new Link<T>(item,NULL);
    }
    else{
        rear->next=new Link<T>(item,NULL);
        rear=rear->next;
    }
    size++;
    return true;
}
bool deQueue(T* item){
    //返回队头元素并从队列中删除
    Link<T>*tmp;
    if(size==0){//队列为空，没有元素可以出队
        cout<<"队列为空"<<endl;
        return false;
    }
    *item=front->data;
    tmp=front;
    front=front->next;
    delete tmp;
    if(front==NULL){
        rear=NULL;
    }
    size--;
    return true;
}
```



## 顺序队列与链式队列的比较

- 顺序队列
  - 固定的存储空间
- 链式队列
  - 可以满足大小无法估计的情况
- ==都不允许访问队列内部元素==



# 队列的应用

- 只要满足先来先满足服务特性的应用均采用队列

  作为其数据组织方式或中间数据结构

- 调度或缓冲
  - 消息缓冲器
  - 邮件缓冲器
  - 计算机硬设备之间的通信也需要队列作为数据缓冲
  - 操作系统的资源管理
- 宽度优先搜索

![img](./algorithm.assets/047fea9a94fbdae40bb83664e00f92ac-1724411809476-100-1724414108617-50.png)





























# 字符串

## 字符串基本概念

### 字符串的逻辑结构

- 特殊的线性表，即元素为==字符（char）==的线性表
- 简称"==串=="，==零个==或==多个字符==/符号构成的有限序列
  - $$n(\geq 0)$$个字符的有限序列，一般记作
    - $$S:c_0c_1c_2……c_{n-1}$$
  - S为串名，$$c_0c_1c_2……c_{n-1}$$是串值
  - $$c_i$$串中$$i$$位置上的字符

