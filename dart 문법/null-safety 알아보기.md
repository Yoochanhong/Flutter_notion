<h3>Null-safety에 대하여</h3>



Flutter 2.0, Dart 2.12부터 Null-safety가 적용되었다.

간단한 개념은 "기본적으로 변수에는 null값이 허용되지 않는다!" 이다.



<h4>Null-safety가 나온 이유?</h4>

~~~dart
bool isBigThanThree(int n) => n > 3;
void main(){
  int value;
  print(isBigThanThree(value));
}
~~~

이 코드의 출력값은 뭐라고 나올까?

<span style="color:red">Error: Non-nullable variable 'value' must be assigned before it can be used.</span>  

null이 아닌 변수 'value'를 매개변수로 넣어야 사용 할 수 있다는 오류메시지가 뜬다.

왜냐하면 value라는 변수에 아무런 값도 넣어주지 않았기 때문이다.

이런 null 오류를 막기 위해서는 어떤 방법이 있을까?

방법은 매개변수를 넣는 모든 함수에 이 변수가 null인지 아닌지 확인하는 작업을 거쳐야 한다.

사실 많이 귀찮다. 매번 null을 체크하는것도 힘들고, 코드양이 많아지면 굉장히 비효율적이게 된다.

그리고 코드가 5만줄 가까이 되는 엄청난 길이의 코드에서 null이 들어가면 안될 변수에 실수로 null값이 들어갔다면?

시스템이 터져버렸을때 어떤 변수에 값이 할당이 안된건지 찾는건 모래에서 바늘찾기와도 같다.

그래서 나온 개념이 "애초에 null값이 없는게 디폴트라면?" 이다.

변수를 선언할때부터 얘가 null인지 아닌지를 체크해주면 null값으로 인한 오류를 상당히 줄일수 있게 된다.



<img src='https://search.pstatic.net/sunny/?src=https%3A%2F%2Fmiro.medium.com%2Fmax%2F1200%2F1*6-SfhIoFLl1NPaNi8Ld8Og.png&type=sc960_832' width=300px/> 




<h4>Null-safety란?</h4>

1. 모든 변수에는 null이 들어갈 수 없다.
2. Nullable 변수에만 null이 들어갈 수 있다.
3. Non-nullable 변수를 위한 null-check가 필요 없다.
4. 클래스 내의 변수는 무조건 선언과 동시에 초기화를 시켜줘야한다.



<h4>Null-safety 문법</h4>

null-safety의 문법으로는 ?, ??, !, required, late가 있다.

먼저, 변수들은 기본적으로 null을 허용하지 않는다.(non-nullable)

변수에 null값이 들어갈수도 있다면 타입 뒤에 ?를 붙여서 nullable임을 명시해주자.

~~~dart
int? a;
a = null;
int b;
b = null;
~~~

변수 a는 nullable임을 명시해줘서 오류가 뜨지 않지만, b는 non-nullable여서 오류가 뜬다.

<span style="color:red">A value of type 'Null' can't be assigned to a variable of type 'int'.</span>

Non-nullable 변수라면 선언과 동시에 초기화를 해주도록 하자.



반대로 절대로 이 변수에는 null이 없다고 확신하는 순간에는 !를 붙여서 명시해준다.

~~~dart
String? name;
name = '유찬홍';
name = null;
print(name!.length);
~~~

name의 길이를 출력해주는 .length를 붙였다. name에는 null이 들어가있지만 컴파일 단계에서는 오류가 나지 않는다.

name 변수에는 null이 없다고 !를 붙였기 때문이다.(물론 런타임시에는 오류가 나니까 이렇게 쓰지 말 것)



클래스 생성자로 null이 아닌 확실한 값을 받아야 할 때가 온다면, required를 붙여서 명시적인 값을 넣어달라고 요청할 수 있다.

~~~dart
class Test{
  int a;
  String b;
  Test({required this.a, required this.b});
}
~~~

인스턴스를 만들때 생성자로 a와 b를 무조건 입력하게 만들어서 에러를 빨리 캐치할 수 있다.



만약 서버통신과 같이 값이 아직 오지 않아서 null인 상태라면,  ?? 를 붙여서 예외 처리를 해줄수 있다.

~~~dart
int? c;
print(c ?? 'There is a null in c.'); // c가 null인 경우에는 ?? 뒤에 있는 값을 출력해주세요.
~~~

출력 결과는 There is a null in c가 나온다.



서버통신을 하다보면 위의 상황처럼 null인 경우가 있다. 서버에서 값을 받아와야 하는데 non-nullable 경우를 만들고 싶다면?

~~~dart
late int d;
print(d + 30); //아직 d는 초기화가 안되서 오류가 난다.
d = 10;
print(d + 30); //40이 출력됨
~~~

이런식으로 타입 앞에 late 키워드를 붙여주면 선언은 하지만 초기화는 나중에 한다는 뜻으로 코드를 적을 수 있다.