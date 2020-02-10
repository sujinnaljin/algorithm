

# Algorithm

## 2019

### 0303

- [9465 스티커](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_9465.java)

  `i`와 `j`의 순서 바뀌면 안됨. 지그재그로 가면서 `dp` 구해야함

  ```java
  for (int i = 2; i < n; i++) {
      for (int j = 0; j < 2; j++) {
          dp[i][j] = Math.max(sticker[i][j]+dp[i-1][(j+1)%2], sticker[i][j]+dp[i-2][(j+1)%2]);
      }
  }
  ```

  

### 0304

- [11723 집합](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_11723.java)

  연산의 수 M (1 ≤ M ≤ 3,000,000) 이 많기 때문에 그대로 출력하면 시간초과. `StringBuilder` 사용

  

### 0305

- [10972 다음 순열](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_10972.java)

   `A[i]` 와 `A[j]`가 아닌, `A[i-1]` 와 `A[j]`를 swap 하는 것에 유의

- [10973 이전 순열](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_10973.java)

  다음 순열에서 `while` 절에 있는 부호 바꾸면 됨

- [10974 모든 순열](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_10974.java)

- [1722 순열의 순서](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_1722.java)

  N(1≤N≤20), k(1≤k≤N!) 처럼 k의 범위가 크기 때문에 자료형  `long` 사용해야함. 안그러면 런타임 에러.

  k가 크기때문에 k번째 순열을 구할때 다음 순열을 반복하기보다  `factorial` 이용해서 풀어야함.



### 0306

- [1476 날짜 계산](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_1476.java)

  나올 수 있는 경우의 수(15\*28\*19)가 작기 때문에 bruteforce 기법도 가능하나, 중국인의 나머지 정리([Chinese Remainder Theorem](https://joonas.tistory.com/23)) 사용 가능

  `x % 15 = e, x % 28 = s, x % 19 = m` 을 만족하는 `x`를 구함

### 0307
- [1001 A-B](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_1001.java)

### 0311

- [4673 셀프넘버](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_4673.java)

### 0314

- [14226 이모티콘](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_14226.java)

  BFS 문제. 다시 풀기

  참고 : https://jaejin89.tistory.com/45

- [11729 하노이 탑 이동 순서](https://github.com/sujinnaljin/algorithm/blob/master/src/com/sopt/algorithm/B_11729.java)

  하노이탑 문제. 다시 풀기
  1. 1에서 n-1개를 2로 옮긴다.
  2. 1에서 1개를 3으로 옮긴다.
  3. 2에서 n-1개를 3으로 옮긴다.

  참고 : https://hyeonstorage.tistory.com/355



### 200205

- [10828 스택](https://www.acmicpc.net/problem/10828)

  **Stack 자료구조**

- ```java
  Stack<Integer> stack = new Stack<>();
  ```

  **BufferedWriter**

  int 출력 시, String으로 변환시켜줘야 함

  **BufferedReader**

  1. 기본적으로 BufferedReader는 **한 줄을 통째로 입력받는 방법**으로 주로 쓰입니다.

  2. **readLine()** 메서드는 값을 읽어올 때, **String값**으로 개행문자(엔터값)를 포함해 **한줄을 전부 읽어오는 방식**입니다.

     비슷한 예로 Scanner메서드 중 nextLine()도 스트링 값과 개행문자(엔터값)을 같이 읽어옵니다.(반면 next()는 개행문자는 제외하고 스트링 값만 읽어옵니다.)

  3. **read()** 메서드는 값을 읽어올 때, **int값으로 변형**하여 읽어오는 방식입니다.

     예를들어 input.txt에 저장된 **1**이라는 숫자를 read()를 통해 읽어오면  int형 숫자 1을 읽어오는 것이 아닌, txt형식으로 저장된 **ASCII 형식의 문자값 '1'**을 읽어오는 것이므로 결국 **int값으론 49**를 읽어오는 것이 됩니다. 

     이를 해결하려면 **int a = br.read() - 48; br.readLine();** 을 하여 ASCII 값에서 뻴셈을 이용한 뒤 엔터 값을 읽어오거나, **int a = Integer.parseInt(br.readLine());** 를 통해 엔터값을 포함해 한줄을 통째로 입력받은 뒤 해당 스트링값을 int로 형변환 해주는 방법이 있습니다.

  출처 : <https://www.acmicpc.net/board/view/9744>

- [드래곤 커브](<https://www.acmicpc.net/problem/15685>)

  이전세대까지 진행된 점들에 대해 역방향으로 그려지는 규칙을 찾는 것이 중요

  참고 <https://limkydev.tistory.com/158>

  ​	<https://dublin-java.tistory.com/34>

  **Swallow Copy , Deep Copy**

  a[i] = b[i]

  이런식으로 배열 복사하면 한쪽 값 수정시 다른 쪽 값도 변경됨.

  = 연산자는 **주소를 이어준다**는 의미이기 때문. 이를 얕은 복사 (swallow copy)라고 함

  값 복사를 위해서는

  - arrayList에서는 `list.copyAll()` 이나, `list.addAll()`;

  - 1차원 배열의 경우 `list.clone()` 로 해결가능하지만 2차원 배열 같은경우 따로 함수 작성 필요.

    ```java
    public static String[][] deepCopy(String[][] original, int n) {
        if (original == null) {
            return null;
        }
    
        String[][] result = new String[n][n];
        for (int i = 0; i < original.length; i++) {
            System.arraycopy(original[i], 0, result[i], 0, original[i].length);
        }
        return result;
    }
    ```

  출처 <https://vivi-world.tistory.com/27>

### 200205

- [17779 개리맨더링2](<https://www.acmicpc.net/problem/17779>)

  풀이 참고 : <https://www.youtube.com/watch?v=sfIseJYH7NE>





## 알고리즘 공부 순서

출처 : https://offline.startlink.help/hc/ko/articles/217245158

1. **알고리즘과 입/출력**

먼저 알고리즘이 무엇인지에 대해서 간략하게 배웁니다. 그 다음, 알고리즘을 공부하는 방법을 배웁니다.

알고리즘에서 가장 중요한 것은 시간이 얼마나 걸릴지 예측하는 능력이기 때문에, 시간 복잡도를 가장 첫 번재로 배웁니다.

알고리즘은 문제 풀이를 통해서 공부하는 것이 가장 효율적이기 때문에, 입/출력을 받는 방법을 배웁니다. 다양한 예제 문제 (A+B)를 통해서 다양한 입력 형식 (단일 입력, 테스트 케이스, EOF)을 처리하는 방법을 배웁니다.



2. **자료구조 1**

알고리즘을 효율적으로 구현하기 위한 자료구조를 배웁니다.

첫 번째로 스택을 배웁니다. 스택이 무엇인지, 어떻게 구현하면 좋을 것인지를 배운 다음 스택을 여려가지 문제를 통해서 응용하게 됩니다. 다른 알고리즘 강의를 들으면 스택을 들은 다음 예제로 한 번 구현해보는 것은 계산기(후위표기식) 입니다. 이 강의에서는 후위 표기식을 이용한 계산기를 구현하지 않습니다. 이유는 직관적이지 않고, 스택보다 다른 구현에 더 많이 신경을 써야 합니다. 5가지 문제를 통해서 각 문제를 해결하는데 있어서 스택을 왜 사용해야 하고, 해결하기 위해 스택을 어떻게 활용하는지 배웁니다.

두 번째로 배우는 것은 큐입니다. 큐는 BFS나 완전 탐색같은 알고리즘을 구현하려면 필수적인 자료구조입니다. 큐는 스택과 다르게 간단하게 다루고 넘어갑니다. 2문제 정도를 풀게 됩니다.

세 번째로는 덱을 배웁니다. 덱은 덱이 무엇인지만 배우고 넘어갑니다.

마지막으로 배우는 것은 바로 문자열입니다. 아스키 코드가 무엇인지, 단어의 길이를 함수를 이용하지 않고 재는 방법, 문자열과 정수 사이의 변환을 배웁니다.



3. **다이나믹 프로그래밍 1**

많은 사람들이 어려워 하는 다이나믹 프로그래밍을 쉽고 이해가기 쉽게 가르칩니다.

먼저, 이번 챕터에서는 다이나믹 프로그래밍이 뭔지를 배우게 되며, 약 20가지 문제 풀이를 통해서 다이나믹 프로그래밍을 연습합니다.



4. **수학 1**

알고리즘을 공부하는데 왜 갑자기 수학이 필요할까요? 

먼저, 알고리즘 대회나 이런 문제 풀이에서 중요한 것은 복잡한 프로그램은 구현 능력이 아니고 문제 해결 능력입니다. 당연히 복잡한 프로그램의 구현 능력도 중요합니다. 간단하고 정제되어있는 문제를 해결하지 못한다면, 복잡하고 정제되어 있지 않은 문제를 풀 수 있을까요? 따라서, 경우의 수가 매우 큰 경우에는 큰 정수의 구현 보다는 나머지 연산을 통해서 정답을 출력하라는 문제를 많이 만날 수 있습니다. 따라서, 첫 번째로 나머지 연산에 대해서 배웁니다.

그 다음은 최대 공약수와 최소 공배수에 대해서 배웁니다.

소수는 약수가 1과 자기자신 밖에 없는 수입니다. 소수는 암호학에서 매우 중요한 역할을 하고 있으며, 알고리즘에서도 소수가 매우 중요합니다. 따라서, 어떤 수가 소수인지 판별하는 방법과, 어떤 정수 범위 안에 들어있는 소수를 구하는 방법을 배웁니다.

마지막으로는 소인수분해를 하는 간단한 방법과 진법 변환, 그리고 팩토리얼에 대한 내용을 조금씩 배우고 넘어갑니다.



5. **정렬**

정렬은 STL의 sort를 응용하는 방법을 배웁니다. O(N^2) 정렬 알고리즘은 다루지 않으며, 강의 때는 O(NlgN) 정렬 알고리즘만 다룹니다. 다양한 데이터를 정렬해야 하는 상황을 제시하며, 이럴 때는 sort의 비교 함수를 어떻게 작성해야 하는지를 배웁니다.

퀵 소트, 머지 소트, 힙 소트같은 유명한 소트 알고리즘은 다루지 않을까요? 아닙니다! 모두 다 강의 시간에 다룹니다. 퀵 소트와 머지 소트는 분할 정복 챕터에서, 힙 소트는 자료구조 2 챕터에서 배웁니다.



6. **그래프 1**

그래프는 가장 자료구조 중의 하나입니다.

그래프가 뭔지, 그래프 용어에 대해서 배웁니다. 

이제, 그래프가 무엇인지 알았기 때문에 그래프를 저장하는 방법 세 가지를 배웁니다. 그 세 가지는 바로 인접 행렬, 인접 리스트, 간선 리스트입니다.

세 가지 중에서 가장 중요하게 다루는 내용은 인접 리스트입니다. 인접 리스트를 사용하면 인접 행렬을 사용했을 때보다 시간과 공간이 더 효율적입니다. 효율적인 알고리즘 구현을 위해서 연결 리스트를 사용하지 않고 STL의 vector를 사용해서 인접 리스트를 구현하는 방법을 배웁니다.

그런데, 연결 리스트를 구현하기도 싫고, 사정상 STL을 사용할 수 없는 곳이라고요? 그런 분들을 위해 간선 리스트라는 자료구조도 준비했습니다. 간선 리스트는 그 어떤 책을 봐도 나오지 않는 신기한 자료구조입니다. 그런 분들을 위해 준비한 자료구조입니다.

이제, 그래프의 탐색에 대해서 배웁니다. 바로 DFS 알고리즘과 BFS 알고리즘입니다. 바로 전에 배운 자료구조 3가지를 이용해서 그래프를 탐색하는 방법을 배우면서 그래프를 저장하는 방법을 다시 한 번 복습하게 됩니다.

이제 DFS와 BFS를 응용할 차례입니다. 따라서, 연결 요소에 대한 내용을 배우고, 이분 그래프에 대한 내용을 배우게 됩니다.

그래프에서 가장 중요한 것은 일반 문제를 그래프로 모델링해서 푸는 것입니다.

그래프 모델링을 연습하기 위해서 사이클을 찾는 연습과 이차원 배열 상에서 플로드 필 알고리즘을 배웁니다.



7. **트리 1**

그래프를 배웠으니 이제 트리를 배울 시간이지요!

트리의 용어에 대해서 배우고, 트리를 순회하는 방법인 프리 오더와 인 오더, 포스트 오더에 대해서 배웁니다.

그 다음에는 그래프와 마찬가지로 트리를 저장하는 방법 세 가지를 배웁니다. 

트리를 저장하는 방법을 배웠으니 트리 문제를 통해서 트리 알고리즘을 연습할 시간이지요. 트리의 부모에 대한 내용과 트리의 지름에 대한 내용으로 트리를 복습합니다.



8. **그리디 알고리즘**

그리디 알고리즘을 배웁니다.

많은 사람들이 착각하는 것이 그리디 알고리즘은 쉽다 입니다. 이 챕터에서는 그리디 알고리즘은 어렵지만 풀 수 있다를 배웁니다.

그리디 알고리즘은 증명이 중요하기 때문에, 일부 문제의 경우는 수업 시간에 증명을 합니다. 

그리디 알고리즘을 잘하는 방법은 다이나믹 프로그래밍과 마찬가지로 다양한 문제를 푸는 것 입니다. 그리디 알고리즘 챕터도 약 10가지 문제를 통해서 연습을 하게 됩니다.



9. **분할 정복**

분할 정복은 문제를 분할한 다음 합쳐서 문제를 푸는 알고리즘입니다.

대표적인 분할 정복 알고리즘인 이분 탐색 알고리즘을 배웁니다. 그 다음에는 대표적인 분할 정복 정렬 알고리즘인 머지 소트와 퀵 소트에 대한 내용을 배웁니다. 다양한 문제를 통해서 분할 정복 알고리즘을 연습합니다.

이 챕터에서 제일 재미있는 내용은 버블 소트에 대한 문제를 머지 소트를 이용해서 푼다는 것입니다.

마지막으로는 분할 정복 알고리즘의 하이라이트인 가장 가까운 두 점을 찾는 방법을 배웁니다.



10. **이분 탐색으로 정답 찾기**

이분 탐색 알고리즘은 정렬된 리스트에 어떤 수가 있는지 없는지를 조사하는 알고리즘입니다.

이 원리를 이용해서 이분 탐색으로 문제를 풉니다.

주로, 정답을 구하기는 어려운데 정답을 검증하기 쉬운 경우에 이 알고리즘을 사용하게 됩니다.



11. **완전 탐색 0 (모든 경우 다 해보기 전에)**

완전 탐색 1에 필요한 두 가지 내용을 먼저 다루는 부분입니다.

이번 챕터에서 비트마스크를 배우네요!

마지막으로 순열을 배웁니다.

다음 순열과 이전 순열, 그리고 모든 순열에 대해서 배우며, 순열의 순서에 대해서도 배웁니다.



12. **완전 탐색 1 (모든 경우 다 해보기)**

여섯 가지의 다양한 알고리즘이 모여있는 챕터입니다.

먼저, 그냥 다 해보는 방법인 부르트 포스(Brute Force)에 대해서 배웁니다. 그 다음, N중 for문을 이용해서 문제를 푸는 방법을 배웁니다. N중 for문은 친구에게 자랑할 때 이외에는 쓸 일이 없기 때문에, 5분만에 다음 챕터로 넘어갑니다.

N개의 일이 있고, 그 일은 모두 해야합니다. 그런데, 순서를 바꿀 수 있습니다. 이런 경우에는 순열을 사용해서 모든 경우를 다 해봐야 합니다. 순열을 이용해서 모든 경우를 중복 없이 다 해보는 방법을 배웁니다.

네 번째로 배우는 알고리즘을 가장 중요한 알고리즘 중의 하나인 바로 BFS를 이용해서 모든 경우를 다 해보는 방법입니다.

다섯 번째로는 재귀 호출을 이용해서 백트래킹을 배우고, 여섯 번째로 비트마스크를 이용해서 모든 경우를 중복 없이 다 해보는 방법을 배웁니다.



13. **자료구조 2**

자료구조 1에서 배웠던 스택을 조금 더 화려하게 사용해봅니다. 중요한 점은 여기에서도 계산기는 만들지 않는다는 것 입니다. 계산기, 후위 표기식은 강의에서 다루지 않습니다!

그 다음으로 배우는 자료구조는 그래프 알고리즘 중에서 크루스칼을 배울 때 필요한 Disjoint-set 입니다.

이제, 안 배운 자료구조가 뭐가 있을까요? 바로 힙입니다. 최대 힙과 최소 힙에 대해서 공부를 하고, 힙을 직접 구현해봅니다. 여기서 배우는 정렬 알고리즘이 힙 소트입니다.

마지막으로 배우는 내용은 이진 검색 트리 (BST) 입니다.



14. **다이나믹 프로그래밍 2**

한 문제를 5가지 방법으로 접근해서 풀어보면서, 다이나믹 프로그래밍에 대한 이해를 높입니다.

그 다음, 다이나믹 프로그래밍 1에서 배운 문제보다 조금 더 어려운 문제를 풉니다.



15. **수학 2**

수학 2는 알고리즘 보다는 다른 문제를 풀 때 필요한 경우가 많아서 배우는 부분입니다.

a^b 제곱 연산을 분할 정복 알고리즘을 이용해서 구하는 방법, 이진수의 원리를 이용해서 구하는 방법을 배웁니다.

그 다음은 행렬에 대한 내용을 간단히 짚고 넘어갑니다.

이제, 피보나치에 관심있는 사람들이 가장 재미있어하는 내용입니다. 바로 피보나치 수에 대해서 배웁니다. 피보나치 수를 구하는 다양한 방법, 피사노 주기, 피보나치 수의 다양한 성질, 피보나치 수를 행렬을 이용해서 구하는 방법을 배웁니다.

이제, 이항 계수를 배울 차례입니다. 이항 계수와 그 응용을 어떻게 하는 지 배웁니다. 여기에서 파스칼의 삼각형도 다루고 넘어갑니다.

카탈란 수에 대해서 들어본 적이 있나요? 이번 챕터에서 배울 수 있습니다!

오일러 피 함수가 무슨 함수인지 아나요? 이 내용도 이번 챕터에서 배울 수 있습니다.

두 수를 나눌 때, 나머지 연산을 어떻게 해야하는지 배우는 챕터가 바로 여기에 있습니다. 수학 1에서는 덧셈, 뺄셈, 곱셈에 대한 나머지 연산만 배우기 때문에, 나눗셈에서 나머지 연산을 하려면 이번 챕터를 꼭 들어야 합니다. 이 내용을 위해 확장 유클리드 알고리즘을 배웁니다.



16. **그래프 알고리즘 2**

다양한 그래프 알고리즘을 배웁니다.

첫 번째로 배우는 그래프 알고리즘은 위상 정렬입니다. 위상 정렬 다음에는 최소 스패닝 트리 (MST)를 구하는 두 가지 방법인 프림과 크루스칼을 배웁니다.

우리가 어딘가로 이동할 때 사용하는 방법은 항상 최단 경로를 사용하는 방법입니다. 따라서, 최단 경로 알고리즘을 이번 챕터에서 배우게 됩니다.

첫 번째로 배우는 최단 경로 알고리즘은 벨만 포드 알고리즘이고, 두 번째로 배우는 알고리즘은 다익스트라 알고리즘, 마지막으로 배우는 알고리즘은 플로이드 와샬 알고리즘입니다. 세 알고리즘을 단순히 설명만 하는 것이 아니고, 구현도 하며, 응용하는 문제도 풀게 됩니다.



17. **트리 2**

트리 2에서는 가장 가까운 공통 조상(LCA)에 대한 내용을 집중적으로 배웁니다.

직관적으로 구현하는 방법과 다이나믹 프로그래밍을 이용해서 구하는 방법을 배웁니다.

두 가지 방법을 배운 다음에는 임의의 두 정점 사이의 거리를 BFS 알고리즘보다 빠르게 구하는 방법에 대해서 배웁니다.



18. **완전 탐색 2**

모든 경우를 다 해보지 않고, 정답이 될 수 있는 것만 다 해보는 일부 경우만 다 해보는 알고리즘, 완전 탐색 1에서 배운 BFS를 덱을 사용해서 하는 방법, 탐색의 규모가 너무 큰 경우에 문제의 크기를 절반으로 나누어서 푸는 중간에서 만나는 알고리즘 (Meet in the Middle) 알고리즘을 배웁니다



19. **구간의 최소값 구하기**

구간의 최소값을 구하는 문제를 그냥 다 해보는 방법, 이차원 배열에 저장해서 구하는 방법, 루트 N으로 나눠서 구하는 방법 (sqrt decomposition), 다이나믹 프로그래밍을 이용해서 구하는 방법, 세그먼트 트리를 이용해서 구하는 방법으로 풀고 배웁니다.

마지막으로는 슬라이딩 윈도우 알고리즘을 배웁니다.



20. **구간의 합 구하기**

구간의 합을 구하는 문제를 누적합을 이용해서 구하는 방법, 세그먼트 트리를 이용해서 구하는 방법, 펜윅 트리(바이너리 인덱스 트리)를 이용해서 구하는 방법으로 풀고 배워봅니다.

구간을 업데이트하는 경우에 사용하는 세그먼트 트리 나중에 업데이트 하기 (Segment Tree Lazy Propagation)도 여기서 배웁니다.

마지막으로, 다양한 문제를 세그먼트 트리나 BIT를 사용해서 풀어봅니다



21. **다이나믹 프로그래밍 3**

비트마스크를 이용해 상태를 나타내고 그 상태를 다이나믹에 이용해 봅니다. 약 10개의 문제를 풀게 됩니다.

마지막으로는 한 문제를 5가지 서로 다른 점화식을 통해서 풀어봅니다.



22. **네트워크 플로우**

그래프에서 가장 중요한 알고리즘인 네트워크 플로우를 배웁니다.

최대 유량이 무엇인지를 배우고, 최대 유량을 구하는 두 가지 알고리즘인 Ford-Fulkerson과 Edmond-Karp에 대해서 배웁니다.

이분 매칭, 민 컷, 최소 버텍스 커버, 최대 독립 집합에 대한 이론과 내용을 공부하고, 문제 풀이에 응용해 봅니다.

이 챕터는 알고리즘보다 그래프를 만드는 방법이 중요하기 때문에, 약 15가지 문제를 이용해 그래프 모델링을 연습해봅니다.



23. **최소 비용 유량 (MCMF)**

최대 유량 문제에서 최소 비용문제가 추가되면 최소 비용 유량 문제가 됩니다. 이를 영어로 줄여서 MCMF라고 합니다.

MCMF도 그래프 모델링이 중요하기 때문에, 네트워크 플로우 챕터처럼 그래프 모델링하는 연습을 해봅니다.



24. **세그먼트 트리 활용하기**

구간의 최소값과 합을 구할 때 사용한 세그먼트 트리를 다른 문제 풀이에 이용해봅니다.

먼저, 분할 정복과 함께 세그먼트 트리를 사용하는 방법을 배우고, 최소값을 찾는 방법을 이용해서 K번째를 찾는 방법을 배웁니다.



25. **네트워크 플로우 문제 풀이**

여러가지 네트워크 플로우 문제를 풀어봅니다.



26. **그래프 알고리즘 3**

먼저 오일러 회로를 구하는 방법을 배웁니다. 그 다음 강한 연결 요소 (SCC)을 구하는 Kosaju's Algorithm과 Tarjan's Algorithm을 배웁니다. 여기서 DFS Tree에 대한 내용도 배웁니다.

그 다음, Tarjan's Algorithm을 응용해 단절점과 단절선을 구하는 방법을 배우고, 문제 풀이로 응용해 봅니다.

마지막으로 배우는 내용은 2-SAT 문제 입니다.



27. **다이나믹 프로그래밍 4**

다이나믹 프로그래밍 4에서는 지금까지 다루지 않았던 다양한 유형의 다이나믹 문제를 풀어봅니다.

트리 다이나믹, 왼쪽과 오른쪽을 왔다갔다 하면서 푸는 다이나믹, 다이나믹 점화식을 통해서 정답을 역추적하는 방법, 확률 다이나믹, 왼쪽과 오른쪽에서 시작해서 가운데로 모이는 다이나믹을 배웁니다.



28. **문자열 알고리즘**

문자열 매칭 알고리즘을 배우는 챕터입니다.

KMP, Trie, Aho-corasick, Suffix Array에 대한 내용을 배웁니다.



29. **기하 알고리즘**

원, 직선, 선분과 같은 도형에 대한 내용, 다각형에 대한 내용을 먼저 배웁니다.

그 다음은 CCW 알고리즘을 배우고, 이를 이용해 선분의 교차를 판별하는 방법을 배웁니다.

어떤 점이 다각형의 내부에 있는지 아닌지, 다각형의 넓이를 구하는 방법을 배우고, 볼록 껍질(Convex Hull)을 구하는 방법인 그라함 스캔(Graham Scan)을 배웁니다.

이제 라인 스위핑 알고리즘(Line Sweeping Algorithm) 을 배울 차례 입니다. 이 알고리즘을 통해서 가장 가까운 두 점을 구해봅니다.

가장 가까운 두 점을 구했으면, 이제 가장 먼 두 점을 구해볼 차례입니다. 로테이핑 캘리퍼 알고리즘(Rotating Calipers)을 이용해서 가장 먼 두 점을 구해봅니다.

겹치는 선분 문제, 직사각형 N개의 합집합을 구하고 기하 알고리즘 강의는 끝나게 됩니다.



30. **알고리즘 게임**

알고리즘 게임 챕터에서는 조합 게임(Combinatorial Game) 문제 중에서 Impartial Game 문제를 푸는 방법을 배웁니다. 

돌 게임(Subtraction Game), 님 게임 (Nim Game)을 푸는 방법을 배우고, The Sprague-Grundy Function을 이용해 조합 게임 문제를 푸는 방법을 배웁니다.

그 다음 다양한 님 게임 변형 문제의 Grundy Number를 구해봅니다



31. **다이나믹 프로그래밍 5**

기댓값 DP와 DP 최적화 (Dynamic Programming Optimization)을 배웁니다.

DP 최적화에서는 Knuth Optimization, Divide & Conquer Optimization, Convex Hull Optimization을 배웁니다.
