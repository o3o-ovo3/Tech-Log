# Java - Collection Framework

:writing_hand: *Assembled by Yunju Jang*

🤝*Contributors : JeongHea Shin, JiYe Bae* 

<hr>



### Java Collection Framework

- <b>Collection 객체</b>
  - 데이터의 집합, 그룹 (컨테이너)
  - 여러 원소들을 담을 수 있는 자료구조이다.
  - 배열과 비슷하지만 크기가 고정된 배열의 문제점을 보완하였다.

<br/>

- <b>Java Collection Framework (JCF)</b>
  - 이러한 데이터, 자료구조의 컬렉션과 이를 구성하는 클래스를 정의하는 인터페이스를 제공한다.
    - 즉, 컬렉션을 다루기 위한 표준화 프로그래밍 방식이다.
  - 배열의 문제점을 해결하고, 널리 알려져 있는 자료구조를 바탕으로 객체들을 효율적으로 추가, 삭제, 검색할 수 있도록 한다.
  - java.util 패키지에 컬렉션과 관련된 인터페이스와 클래스들을 포함시킨 것이다.
    - 컬렉션 인터페이스 : java.util 패키지
    - 컬렉션 클래스 : java.util 또는 java.util.concurrent 패키지

<br/>

<br/>

- <b>컬렉션 프레임워크 사용 시 장점</b>

  - 코딩 시간이 감소한다.

  - 코드의 품질을 보장한다.

  - 유지보수 시간이 감소한다.

  - 재사용이 가능하고 상호 운용성이 보장된다.

    > 상호 운용성
    >
    > - 하나의 시스템이 동일 또는 이기종의 다른 시스템과 아무런 제약 없이 서로 호환되어 사용할 수 있는 성질

<br/>

<br/>

- <b>컬렉션 프레임워크 계층 구조</b>

  - Collection 인터페이스는 크게 List, Set, Queue 로 3개의 상위 인터페이스로 분류한다.

  - Map의 경우 Collection 인터페이스를 상속받고 있지 않지만 Collection으로 분류한다.

    - Map은 구조상의 차이(Key-Value)로 인해 별도로 정의한다.

    <img src='resources/JCF.png' width='450px' align='center'>

    

  <br/>

  - Collection 인터페이스

    - 데이터를 순서, 집합 형태의 저장 공간에 담는다.
    - Set : 순서를 유지하지 않은 상태로 데이터를 저장하고, 동일한 데이터를 중복 저장할 수 없다.
    - List : 순서를 유지한 상태로 데이터를 저장하고, 중복 저장이 가능하다.
    - Queue : List와 흡사하며, 처리 전 요소를 보유하는데 사용한다.

    <img src='resources/collections.png' width='500px' align='center'>

    

  <br/>

  - Map 인터페이스

    - Key-Value 형태의 저장 공가에 데이터를 담는다.
    - Map : Key와 Value를 하나의 쌍으로 묶어서 관리하고, Key는 중복으로 저장할 수 없다.

    <img src='resources/map.png' width='400px' align='center'>

<br/>

<br/>

<br/>

##### Collection Interface

- 표현 방법
  - 제네릭(Generics)로 표현한다.
    - 컴파일 시점에서 객체의 타입을 체크하기 때문에 런타임 에러를 줄일 수 있다.
  - 클래스를 자료형에 상관없이 사용할 수 있다.

<br/>

- 컬렉션 인터페이스 분류

  - <mark>Collection 인터페이스</mark>

    - 직접적인 구현은 제공하지 않고, 모든 컬렉션 클래스가 구현해야 하는 메소드를 포함하고 있다.

    <br/>

    1) List 인터페이스

    - 순서가 있는 컬렉션이며, 중복 요소를 포함할 수 있다.
    - 인덱스로 모든 요소에 접근할 수 있다.
    - 구현 클래스  : ArrayList, LinkedList

    <br/>

    2) Set 인터페이스

    - 중복 요소를 포함할 수 없고 랜덤 액세스를 허용하지 않는다.
    - iterator 또는 foreach를 이용하여 요소를 탐색할 수 있다.
    - 구현 클래스 : HashSet, TreeSet, LinkedHashSet

    <br/>

    3) Sorted 인터페이스

    - 요소를 오름차순으로 유지하는 Set이다.

    <br/>

    4) Queue 인터페이스

    - 처리 전의 요소를 보유하는 데 사용한다.
    - FIFO 정렬, 예외적으로 우선순위 큐가 존재한다.

    <br/>

    5) Dequeue 인터페이스

    - 양쪽 끝에 요소 삽입 및 제거를 지원한다.

    <br/>

    <br/>

  - <mark>Map 인터페이스</mark>

    - 키와 값을 매핑한다.
    - 중복 키가 존재할 수 없으며 각 키는 하나의 값만 매핑할 수 있다.
    - Map의 기본 연산
      - put, get, containsKey, containsValue, size, isEmpty 등
    - 구현 클래스 : HashMap, TreeMap, LinkedHashMap

    <br/>

    - SortedMap 인터페이스 : 매핑을 오름차순의 키 순서로 유지하는 Map

    <br/>

  - <mark>기타 인터페이스</mark>

    - Iterator 인터페이스

      - 어떤 컬렉션이든 반복적으로 수행하기 위한 메서드 제공

      - 컬렉션 프레임워크에서는 Enumeration 대신 Iterator를 사용한다.

        > Enumeration 인터페이스
        >
        > - 객체들의 집합(Vector)에서 각각의 객체들을 한 순간에 하나씩 처리할 수 있는 메소드를 제공하는 컬렉션이다.

      - 컬렉션 클래스의 Iterator 는 Iterator 디자인 패턴을 구현한다.

      - iterator 메서드를 통해 컬렉션으로부터 iterator instance를 가져올 수 있고, 컬렉션을 순회하는 도중에 엘리먼트들을 삭제할 수 있다.

      <br/>

    - ListIterator 인터페이스

      - Iterator를 상속한 인터페이스로, List에서 제공하는 인터페이스이다.
        - List 인터페이스에서만 listIterator() 메서드를 사용할 수 있다.
      - 어느 방향이든 (양방향) 목록을 탐색하고 반복하면서 목록을 수정하고, 목록에서 반복자의 현재 위치를 가져올 수 있다.

      - ListIterator에는 현재의 요소가 없다.
        - 커서 위치는 항상 previous()에 대한 호출에 의해 반환될 요소와 next()에 대한 호출에 의해 반환될 요소 사이에 위치한다.

      <br/>

<br/>

<br/>

##### 컬렉션 클래스

- 컬렉션 클래스란?
  - 컬렉션 프레임워크가 제공하는 컬렉션 인터페이스에 대한 구현 클래스

<br/>

- 컬렉션 클래스의 종류
  - 일반적으로 쓰이는 클래스
    - ArrayList, LinkedList, HashSet, TreeSet, PriorityQueue, ArrayDeque, HashMap, TreeMap, LinkedHashMap
  - Concurrent 클래스
    - CopyOnWriteArrayList, ConcurrentHashMap, CopyOnWriteArraySet
  - Legacy 클래스
    - Vector, Stack, Dictionary, Hashtable, Properties
  - Abstract 클래스
    - AbstractList, AbstractSequenctailList, AbstractSet, AbstractQueue

<br/>

- 특징

  | 컬렉션 클래스        | 순서 | 랜덤 액세스 | 키 - 값 | 중복 요소 | 널 요소 | 스레드 안전 |
  | -------------------- | ---- | ----------- | ------- | --------- | ------- | ----------- |
  | ArrayList            | O    | O           |         | O         | O       |             |
  | LinkedList           | O    |             |         | O         | O       |             |
  | HashSet              |      |             |         |           | O       |             |
  | TreeSet              | O    |             |         |           |         |             |
  | Hashmap              |      | O           | O       |           | O       |             |
  | Treemap              | O    | O           | O       |           |         |             |
  | CopyOnWriteArrayList | O    | O           |         | O         | O       | O           |
  | CopyOnWriteArraySet  |      |             |         |           | O       | O           |
  | ConcurrentHashMap    |      | O           | O       |           |         | O           |

<br/>

<br/>

<br/>

##### 컬렉션즈 클래스 

- 컬렉션즈 클래스란?

  - collection 인터페이스를 구현한 클래스에 대한 객체 생성, 정렬, 병합, 검색 등의 기능을 안정적으로 수행하도록 도와주는 역할을 한다.
  - 컬렉션에서 작동하거나 반환하는 정적(static) 메서드로만 구성된다.
    - 따라서 인스턴스를 생성하지 않고 바로 사용 가능하다.
  - Collections와 Collection은 다르다.
    - Collection은 인터페이스, Collections는 클래스
  - 자주 사용되는 알고리즘으로는 정렬(sorting), 섞기(shuffling), 탐색(searching) 등이 있다.

  <br/>

- 주요 메서드

  | 메서드                   | 내용                                                         |
  | ------------------------ | ------------------------------------------------------------ |
  | max()                    | 지정된 컬렉션에서 최대 요소 반환 (인덱스 X)                  |
  | min()                    | 지정된 컬렉션에서 최소 요소 반환 (인덱스 X)                  |
  | sort()                   | 지정된 컬렉션을 정렬<br />오버로드 메서드들이 존재하며 가장 기본적인 메소드는 자연순서에 따라 내림차순으로 정렬 |
  | shuffle()                | 지정된 컬렉션의 요소들의 순서를 무작위로 섞음                |
  | synchronizedCollection() | 지정된 컬렉션에 의해 지원되는 동기화 된 컬렉션을 재생성해 반환 |
  | binarySearch()           | 지정된 컬렉션에서 이진 탐색 알고리즘을 사용해 지정된 객체를 검색해 인덱스 반환 |
  | disjoint()               | 2개의 지정된 컬렉션들에서 공통된 요소가 하나도 없는 경우 true를 반환 |
  | copy()                   | 지정된 컬렉션의 모든 요소를 새로운 컬렉션으로 복사 후 반환   |
  | reverse()                | 지정된 컬렉션에 있는 순서를 역으로 변경                      |

<br/>

<br/>

<br/>

##### 컬렉션 프레임워크의 모범 사례

- 크기(size)가 고정되어 있다면 ArrayList 보다 Array를 사용한다.
- 맵에 삽입된 순서대로 iterate를 하고 싶다면 TreeMap을 사용하는 것이 좋다.
- 중복을 허용하고 싶지 않으면 Set을 사용한다.
- 몇몇 컬렉션 클래스들은 초기 용량을 지정할 수 있다.
  - 만약 저장할 요소들의 사이즈를 알 경우에 초기 용량을 지정함으로써 rehashing이나 resizing이 일어나는 것을 회피할 수 있다.
- 코드를 작성할 때, 구현 클래스가 아닌 인터페이스를 기반으로 작성해야 나중에 구현체를 변경할 때 코드를 재작성하는 수고를 줄일 수 있다.
- 런타임에 발생할 수 있는 ClassCastException을 회피하려면 항상 제네릭 타입을 사용하여 type-safety한 상태를 유지하도록 한다.
- 맵에 키를 사용할 때 JDK에서 제공하는 immutable 클래스를 사용하여 사용자 클래스에서 hashCode()와 equals() 를 구현할 필요가 없도록 한다.
- 읽기 전용 및 동기화, 빈 컬렉션 등을 만들 때는 자신만의 구현으로 생성하지 말고, collections에서 제공하는 유틸리티 클래스를 사용한다.
  - 이는 코드의 재사용성을 높여주고, 안정적이며, 유지보수 비용을 줄여준다.

<br/>

<br/>

<br/>

## 예상질문❔

Q1) 컬렉션이란 무엇인가?

Q2) 여러 원소들을 담을 수 있는 자료구조로, 배열과 비슷하지만 크기가 고정된 배열의 문제점을 보완한 것이다.

<br/>

Q2) 자바 컬렉션 프레임워크란 무엇인가?

A2) 컬렉션을 다루기 위한 표준화 프로그래밍 방식이다. 배열의 문제점을 해결하고, 널리 알려져 있는 자료구조를 바탕으로 객체들을 효율적으로 추가, 삭제, 검색할 수 있도록 한다.

<br/>

<br/>

### Reference📖

- [Java 컬렉션 정리1](https://gangnam-americano.tistory.com/41)
- [Java 컬렉션 정리2](https://www.crocus.co.kr/1553)
- [Java 컬렉션 정리3](https://gbsb.tistory.com/247#java-collections-algorithms)
- [Java 컬렉션 정리4](https://shlee0882.tistory.com/97)
- [상호운용성](https://ko.wikipedia.org/wiki/상호운용성)
- [Enumeration](https://hyeonstorage.tistory.com/210)
- [[Java\] Collection Framework1 - List(ArrayList / Vector / LinkedList)](https://minhamina.tistory.com/14)
- [자바 컬렉션 프레임워크(Java Collection Framework) 정리](https://gbsb.tistory.com/247)
- [[JAVA\] Java 컬렉션(Collection) 정리](https://gangnam-americano.tistory.com/41)
- [[Java\] 컬렉션 프레임워크 - List, Set, Queue, ArrayList, LinkedList, Iterator, Stack, Tree, Map](https://butter-shower.tistory.com/89)
- [자바공부-5.List 인터페이스와 ListIterator 인터페이스](https://scarlett.tistory.com/entry/자바공부-5List-인터페이스와-ListIterator-인터페이스)
- [Collections 클래스](https://velog.io/@gillog/Collections-클래스)
