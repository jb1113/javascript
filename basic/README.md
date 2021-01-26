# JavaScript의 기초

- JavaScript의 데이터 타입

    컴퓨터 프로그래밍에서는 많은 데이터를 처리하게 되고, 이를 위해서는 특히 데이터를 종류별로 분류하는 일은 아주 중요합니다.
    JavaScript 또한 다양한 데이터 타입이 존재합니다.
    크게 6종류의 데이터 타입이 있지만, 그 중 JavaScript에서 가장 많이 사용하는 데이터 타입으로 숫자(Number)와 문자열(String)이 있습니다.

    ### 숫자(Number)

    숫자 데이터 타입의 가장 중요한 점은 연산이 가능하다는 것입니다.
    1+1에서는 +라는 연산이 왼쪽에 있는 값과 오른쪽에 있는 값을 더해서 하나의 값을 만들어내게 됩니다.
    그렇기 때문에 +를 이항 연산자라고 부릅니다.
    또는 계산을 하기 때문에 산술 연산자라고 부르기도 합니다.
    흔히 사용하는 사칙 연산(+, -, *, /)는 모두 산술 연산자에 속합니다.
    사칙 연산을 이용해서 숫자 데이터 타입을 계산할 수 있습니다.

    ### 문자열(String)

    문자열을 따옴표로 시작해서 따옴표로 끝나게 됩니다.
    작은 따옴표로 시작하면 작은 따옴표로 끝내고, 큰 따옴표로 시작하면 큰 따옴표로 끝내면 됩니다.
    문자열에서 흔히 사용하는 연산으로 length가 있습니다.
    문자열 뒤에 .을 붙이고 length를 입력하면 그 문자열의 길이를 알려주게 됩니다.

    그 외에도 문자를 처리하는 데 다양한 명령어를 사용할 수 있습니다.
    예를 들면 str.toUpperCase()를 사용하면 str안에 들어 있는 모든 문자열의 문자들이 대문자로 바뀌게 됩니다.
    str.indexOf('str')을 하면 str안에 있는 str이라는 문자열을 찾아서 그 부분이 앞에서부터 몇번째 문자인지 알려주게 됩니다.

    문자열을 처리하는 데에는 정말 다양한 명령어가 사용될 수 있습니다.
    이렇게 많은 명령어들을 다 외울 필요는 없습니다.
    필요한 경우 검색을 통해서 필요한 명령어를 쉽게 알아낼 수 있습니다.

    ### 데이터 타입의 중요성

    그렇다면 이제 조금 전 숫자 데이터 타입에서 봤던 연산을 문자열에 적용해 보겠습니다.

    ```jsx
    1+1
    > 2
    "1"+"1"
    > "11"
    ```

    여기에서 "1"은 따옴표로 둘러싸여 있기 때문에 문자열 입니다.
    때문에 결과값은 2가 아닌 "11"이 되었습니다.
    즉, 문자열인지 숫자인지에 따라 연산의 결과가 크게 달라질 수 있다는 것입니다.

    ---

    ### 참고자료

    [JavaScript data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

    [JavaScript Data Types](https://www.w3schools.com/js/js_datatypes.asp)

- 변수와 대입연산자

    수학 문제를 풀 때 우리는 흔히 숫자를 x와 같은 문자에 대입해서 사용합니다.
    이를 변수라고 부르고, 이는 프로그래밍에서도 아주 많이 사용됩니다.
    그렇다면 우리는 이러한 변수를 왜 사용하게 되는 것일까요?

    ### 변수

    변수란 말 그대로 바뀔 수 있는 수를 말합니다.

    ```jsx
    x = 1;
    y = 1;
    x + y;
    ```

    마지막 줄에서 x + y의 값은 어떻게 될까요? 생각하는대로 값은 2가 될 것입니다.
    이어서 아래의 코드를 이어서 실행한다면 어떻게 될까요?

    ```jsx
    x = 1000;
    x + y ;
    ```

    같은 x + y이지만, x의 값이 1000으로 바뀌었기 때문에 결과는 1001이 됩니다.
    여기서의 x처럼 값이 바뀔 수 있는 것을 변수라고 합니다.
    이때 **=** 는 **대입 연산자**라고 부릅니다. 왼쪽에 있는 변수에 오른쪽에 있는 숫자를 대입한다는 의미입니다.
    하지만 다음 코드를 실행할 경우 어떻게 될까요?

    ```jsx
    1 = 2;
    ```

    실행해보면 에러가 나게 됩니다. 이유가 무엇일까요?
    바로 1은 변수가 아니기 때문입니다. 1은 언제나 1이죠.
    이렇게 바뀌지 않는 수를 **상수**라고 합니다.

    ### 변수의 필요성

    그렇다면 변수는 왜 사용하는 것일까요? 그 이유는 무척 다양합니다.
    그중 하나의 이유는 바로 변수를 이용해서 여러군데 흩어져 있는 값들을 한 번에 바꿀 수 있다는 점입니다.
    예를 들어 한 문자열 안에서 같은 "hello"라는 단어가 여러 번 나올 때, 이를 모두 "hi"로 바꾸고 싶다고 해 봅시다.
    이 때 모든 "hello"들이 변수로 나타나 있다면, 변수만 바꿔주면 한 번에 모든 "hello"들을 "hi"로 바꿀 수 있다는 것이죠.
    변수를 쓸 때 한가지 알아두면 좋은 점은 다음 코드와 같이 변수 이름 앞에 var를 붙이면 좋다는 점입니다.
    이 때 var는 변수의 영어 단어인 variable의 약자입니다.

    ```jsx
    var word = "hello"
    ```

    ---

    ### 참고자료

    [Grammar and types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types)

    [var](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/var)

    [JavaScript Variables](https://www.w3schools.com/js/js_variables.asp)

- 비교연산자와 Boolean

    조건문을 만들기 위해서는 먼저 조건을 만들 수 있어야 합니다.
    이를 위해서 필요한 것이 바로 비교 연산자와 Boolean 입니다.
    비교 연산자를 통해서 두 값을 비교하고, 그 결과를 Boolean을 통해서 알아내고, 이를 조건으로 이용합니다.

    ### 동등 비교 연산자 (===)

    JavaScript에서 가장 많이 쓰이는 비교 연산자는 동등 비교 연산자(===)입니다.
    이 비교 연산자는 왼쪽과 오른쪽이 같은지 판단하는 것입니다.

    ```jsx
    1 === 1;
    ```

    이를 출력해보면, True라는 결과를 볼 수 있습니다.
    즉, 왼쪽의 1과 오른쪽의 1이 같다는 것입니다.

    ```jsx
    1 === 2;
    ```

    이 코드의 출력 결과는 False가 됩니다.
    즉, 왼쪽의 1과 오른쪽의 2는 같지 않다는 뜻입니다.

    여기서 알 수 있는 점은 동등 비교 연산자(===)는 이항 연산자라는 것입니다.
    즉 좌항과 우항을 결합해서 그 관계에 따라 하나의 결과, 즉 True인지 False인지를 만들어냅니다.

    ### Boolean

    이렇게 비교 연산자를 사용하면 결과로 True 혹은 Flase가 만들어집니다.
    이 때 이 True와 False를 불리언(Boolean) 데이터 타입이라고 부릅니다.
    우리가 이전에 배웠던 데이터 타입인 숫자(Number)나 문자열(String)에는 아주 많은 종류가 있습니다.
    하지만 Boolean에는 True 아니면 False, 단 두가지만이 존재합니다.

    ### 비교 연산자 <, >

    또 다른 비교 연산자로는 두 값의 크기를 서로 비교하는 연산자가 있습니다.
    우리가 흔히 부등호라고 부르는 <, >와 같은 것들입니다.
    이를 HTML에서 쓸 때는 다음과 같이 씁니다.

    ```html
    <!-- < (Less Than) -->
    &lt;

    <!-- > (Greater Than) -->
    &gt;
    ```

    HTML에서 이 꺽쇠 기호(<, >)가 태그를 나타낼 때 쓰이기 때문에 혼란을 줄 수 있습니다.
    &lt; 가 < 를 의미하는 것이고, &gt; 가 > 를 의미합니다.
    JavaScript에서는 그대로 <, >로 나타내도 괜찮습니다.

    ```jsx
    1 < 1
    ```

    이 코드는 오른쪽 1이 왼쪽 1보다 크다는 의미가 됩니다.
    하지만 이는 거짓이기 때문에 결과는 False가 됩니다.

- 조건문

    ### 조건문이란?

    조건문이란 프로그램이 조건에 따라서 다른 기능들이 다른 순서에 따라서 실행되도록 만들어주는 것입니다.
    조건문은 단순하고 반복적인 업무 뿐만 아니라 복잡한 업무까지도 컴퓨터가 다룰 수 있도록 해줍니다.

    ### 조건문

    ```jsx
    <script>
    	document.write('1<br>');
    	if (true) {
    		document.write('2<br>');
    	} else {
    		document.write('3<br>');
    	}
    	document.write('4<br>');
    </script>
    ```

    위 코드를 실행한 결과로 1 2 4라는 결과가 출력되는 것을 확인할 수 있습니다.
    3은 출력되지 않습니다.

    ```jsx
    <script>
    	document.write('1<br>');
    	if (false) {
    		document.write('2<br>');
    	} else {
    		document.write('3<br>');
    	}
    	document.write('4<br>');
    </script>
    ```

    위 코드를 실행하게 되면 아까와는 달리 1 3 4라는 결과가 출력되게 됩니다.
    그렇다면 if(true)와 if(false), 그리고 else가 어떤 역할을 하길래 이런 결과가 나오는 것일까요?

    if문의 괄호 안에는 Boolean 데이터 타입이 옵니다.
    그리고 만약 그 Boolean이 true이면 if의 첫번째 중괄호에 있는 코드가 실행되고, else의 두번째 중괄호에 있는 코드는 무시됩니다.
    반대로 Boolean이 false이면 if의 첫번째 중괄호는 무시되고, else의 두번째 중괄호에 있는 코드가 실행됩니다.

    ### 조건문을 활용한 토글 만들기

    아래와 같은 button이 있다고 가정해 봅시다.

    ```jsx
    <input type="button" id="toggle" value="dark">
    ```

    이 버튼의 value값을 기준으로, 이 value가 dark이면 light 버전으로 바뀌는 코드를, value가 light이면 dark 버전으로 바뀌는 코드를 실행하도록 프로그램을 만들겁니다.

    이 버튼의 onclick 속성 안에 다음과 같은 JavaScript 코드를 작성합니다.

    ```jsx
    <input type="button" id="toggle" value="dark" onclick="
    	if(???) {
    		document.querySelector('body').style.backgroundColor = 'black';
    		document.querySelector('body').style.color = 'white';
    	} else {
    		document.querySelector('body').style.backgroundColor = 'white';
    		document.querySelector('body').style.color = 'black';
    	}
    ">
    ```

    그렇다면 저 ??? 속에는 어떤 코드가 들어가야 할까요?
    우선은 document에서 id가 toggle인 버튼을 찾아서, 그 버튼의 value가 'dark'인지 아닌지를 알아내야 합니다.
    이를 위해서 다음과 같은 코드를 사용합니다.

    ```jsx
    document.querySelector('#toggle').value
    ```

    현재 페이지에서 querySelector를 사용해서 id가 toggle인 태그를 찾기 위해서 id를 나타내는 #을 붙여줍니다.
    그리고 찾아낸 태그의 value를 알기 위해서 .value 속성을 사용합니다.

    이렇게 가져온 value 값을 dark와 비교하면 됩니다.

    ```jsx
    <input type="button" id="toggle" value="dark" onclick="
    	if(document.querySelector('#toggle').value === 'dark') {
    		document.querySelector('body').style.backgroundColor = 'black';
    		document.querySelector('body').style.color = 'white';
    	} else {
    		document.querySelector('body').style.backgroundColor = 'white';
    		document.querySelector('body').style.color = 'black';
    	}
    ">
    ```

    하지만 이렇게만 작성하게 되면 버튼이 눌릴때마다 value가 바뀌지 않습니다.
    그렇기 때문에 항상 원래 설정된 value인 dark에 해당하는 코드인 첫번째 중괄호의 코드만 실행되게 됩니다.
    이를 해결하기 위해서는 코드가 실행될 때마다 해당 버튼의 value 값을 바꿔주는 코드를 추가해 주어야 합니다.

    ```jsx
    <input type="button" id="toggle" value="dark" onclick="
    	if(document.querySelector('#toggle').value === 'dark') {
    		document.querySelector('body').style.backgroundColor = 'black';
    		document.querySelector('body').style.color = 'white';
    		document.querySelector('#toggle').value = 'day';
    	} else {
    		document.querySelector('body').style.backgroundColor = 'white';
    		document.querySelector('body').style.color = 'black';
    		document.querySelector('#toggle').value = 'dark';
    	}
    ">
    ```

- 리팩토링(중복의 제거)

    하나의 기능을 하는 코드를 만들기 위해서는 다양한 방법이 존재합니다.
    그렇다면 이렇게 다양한 코드 중에서 어떤 것이 가장 좋은 코드일까요?
    작성한 코드를 조금 더 효율적이고 간결하게 만드는 과정을 리팩토링(Refactoring)이라고 합니다.
    리팩토링을 통해 코드의 중복을 제거하고 더 간결하고 가독성 높은 코드를 만들 수 있습니다.

    ### 리팩토링

    리팩토링이란 비효율적인 코드를 효율적으로 만들어서 가독성을 높이고 유지보수가 쉽도록 만드는 것입니다.
    코드의 기능적인 면에서는 변화가 없습니다.

    이전에 작성했던 아래의 코드를 리팩토링하면 어떻게 변경해야 할까요?

    ```jsx
    <input type="button" id="toggle" value="dark" onclick="
    	if(document.querySelector('#toggle').value === 'dark') {
    		document.querySelector('body').style.backgroundColor = 'black';
    		document.querySelector('body').style.color = 'white';
    		document.querySelector('#toggle').value = 'day';
    	} else {
    		document.querySelector('body').style.backgroundColor = 'white';
    		document.querySelector('body').style.color = 'black';
    		document.querySelector('#toggle').value = 'dark';
    	}
    ">
    ```

    여기에서는 자기가 속한 버튼을 찾기 위해서 document.querySelector('#toggle') 이라는 코드를 사용했습니다.
    하지만 만약 이 코드를 복사해서 하나의 버튼을 더 만들게 된다면 어떻게 될까요?
    제대로된 동작을 하지 않을겁니다.

    id는 하나의 태그에만 적용될 수 있으므로 새롭게 만들어진 버튼에는 새로운 id값을 적용해 주어야 합니다.
    예를 들어 새롭게 만든 버튼의 id를 toggle2라고 만들었다고 해봅시다.
    그렇게 되면 이 코드에서 모든 toggle을 toggle2로 직접 바꿔주는 작업을 진행해야 합니다. 무척 비효율적입니다.

    ### this 키워드 사용하기

    그래서 JavaScript에는 자기 자신을 가리키기 위한 this라는 키워드가 있습니다.
    document.querySelector('#toggle')대신 this를 쓸 수 있습니다.

    ```jsx
    <input type="button" id="toggle" value="dark" onclick="
    	if(this.value === 'dark') {
    		document.querySelector('body').style.backgroundColor = 'black';
    		document.querySelector('body').style.color = 'white';
    		this.value = 'day';
    	} else {
    		document.querySelector('body').style.backgroundColor = 'white';
    		document.querySelector('body').style.color = 'black';
    		this.value = 'dark';
    	}
    ">
    ```

    this를 사용하여 변경한 코드가 이전의 코드보다 훨씬 간결해진 것을 확인할 수 있습니다.
    그 뿐만 아니라, 이 코드는 몇 번을 복사해서 붙여넣더라도 따로 추가적인 수정 없이 계속해서 사용할 수 있습니다.

    ### 중복 제거하기

    두 번째로 리팩토링 해 볼 부분은 바로 document.querySelector('body') 부분입니다.
    이 부분이 무려 4번이나 등장하고 있습니다.
    코딩을 할때에는 중복을 없애주는 것이 중요합니다.

    ```jsx
    <input type="button" id="toggle" value="dark" onclick="
    	var target = document.querySelector('body');
    	if(this.value === 'dark') {
    		target.style.backgroundColor = 'black';
    		target.style.color = 'white';
    		this.value = 'day';
    	} else {
    		target.style.backgroundColor = 'white';
    		target.style.color = 'black';
    		this.value = 'dark';
    	}
    ">
    ```

    이렇게 하게되면 target이라는 변수를 만들어서 거기에 body 태그를 찾아서 넣고, 이 target 변수만 간단하게 사용해서 코드의 길이를 줄일 수 있습니다.
    그 뿐만 아니라 target의 값만 변경해주면 나머지 target이 쓰이는 네 줄의 target 값을 모두 바꿀 수 있다는 장점도 있습니다.

- 배열

    프로그래밍을 하다 보면 아주 많은 데이터를 다루게 되는 경우가 생깁니다.
    실생활에서는 이런 경우에 수납장이나 상자를 이용해서 비슷한 물건들을 정리합니다.
    이런 역할을 하는 것이 바로 배열입니다.
    배열은 반복문에 꼭 필요합니다.

    ### 배열(Array)

    우리가 집에 있는 물건들을 정리하기 위해서 서랍장이나 상자에 정리해서 넣듯이 프로그래밍에서도 많은 데이터를 종류별로 정리하는 방법이 필요합니다.
    즉, 배열은 서로 연관된 데이터를 정리해서 담아두는 수납상자라고 생각하면 됩니다.

    배열을 만들기 위해서 어떠한 문법을 사용해야 하는지 알아봅시다.

    ```jsx
    var fruits = ['apple', 'banana'];
    ```

    배열은 다음과 같이 대괄호로 표시합니다.
    그리고 이 대괄호 안에 넣을 값들을 콤마(,)로 구분해서 넣어줍니다.
    그리고 이를 변수 fruits에 넣어줍니다. 즉, 과일을 fruit라는 상자에 넣어준 것입니다.

    ### 배열의 값에 접근하기

    그렇다면 이렇게 만든 배열에 들어있는 내용을 꺼내기 위해서는 어떻게 해야 할까요?

    ```jsx
    document.write(fruits[0]);
    ```

    이렇게 하면 화면에 apple이 출력됩니다. 0 대신 1을 써주면 banana가 출력됩니다.
    즉, 앞에서부터 0번째, 1번째, ... n번째로 순서를 매겨서 그 번호에 해당하는 값을 출력합니다.

    ### 배열의 길이

    배열의 길이를 알아내기 위해서는 다음과 같이 사용합니다.

    ```jsx
    document.write(fruits.length);
    ```

    배열 뒤에 .length를 쓰면 그 배열의 길이를 나타내줍니다.
    이때 출력값은 2가 됩니다.
    즉, 배열에서 내용을 꺼낼때에는 0부터 순서를 매기지만, 길이를 출력할 때에는 1부터 세서 2개의 값이 있으니 2를 출력하는 것입니다.

    ### 배열에 값 추가하기

    배열에 새로운 값을 추가하는 방법입니다.

    ```jsx
    fruits.push('coconut');
    ```

    이렇게 하면 fruits라는 배열의 맨 뒤에 'coconut'이라는 값을 추가해줍니다.
    즉, fruits는 ['apple', 'banana', 'coconut']이 됩니다.

    이 외에도 JavaScript에서는 배열에 대한 다양한 함수들이 존재합니다.
    더 알아보기 위해서는 인터넷에 "javascript array" + "원하는 키워드"로 검색해보면 됩니다.

- 반복문

    프로그래밍을 하다 보면 같은 코드를 여러 번 실행해야 하는 경우가 생기게 됩니다.
    이럴때마다 같은 코드를 계속해서 작성한다면 보기에 좋지 않은 코드가 됩니다.
    이를 해결하기 위해 등장한것이 반복문입니다.

    ### 반복문

    반복문이란 같은 작업을 반복적으로 실행해주는 JavaScript의 새로운 문법입니다.
    예를 들어서 다음과 같은 코드가 있습니다.

    ```jsx
    var links = document.querySelectorAll('a');
    var i = 0;

    while (i < links.length) {
    	links[i].style.color = 'blueviolet';
    	i = i + 1;
    }
    ```

    먼저 첫번째 줄에서는 이 페이지의 모든 `<a>` 태그를 가져옵니다.
    그리고 그 다음줄부터는 반복문을 이용해서 각각의 `<a>` 태그들의 color를 바꾸어 줍니다.

    ### 반복문이 필요한 이유

    다음과 같은 코드가 있습니다.

    ```jsx
    <ul>
    	<script>
    		document.write('<li>1</li>');
    		document.write('<li>2</li>');
    		document.write('<li>3</li>');
    		document.write('<li>4</li>');
    	</script>
    </ul>
    ```

    이 코드를 실행하면 화면에 1, 2, 3, 4가 순서대로 출력됩니다.
    각 줄의 코드가 순서대로 실행됩니다.
    그런데 이 때 2번과 3번이 반복적으로 여러번 실행되어야 한다고 생각해봅시다.
    그러면 2번과 3번 코드를 여러번 복사, 붙여넣기를 하면 됩니다.
    하지만 반복회수가 아주 커진다면 붙여넣기도 힘들고, 코드를 수정하기도 힘들겁니다.
    이때 사용하는 것이 바로 반복문입니다.

    ### while 반복문

    while 반복문은 다음과 같이 사용합니다.

    ```jsx
    while (???) {
    	document.write('<li>2</li>');
    	document.write('<li>3</li>');
    }
    ```

    이때 ???에는 조건문 if문에서 살펴본 것과 같이 조건의 결과인 Boolean 데이터 타입이 들어갑니다.
    그리고 이 조건이 true라면 중괄호 안의 코드를 실행합니다.
    이 코드를 다 실행하고나면 다시 처음으로 돌아가서 ???에 들어간 조건의 Boolean 값을 살펴봅니다.
    이 조건의 Boolean 값이 false가 될 때까지 반복해서 코드를 실행하는 것입니다.

    즉 반복문과 조건문은 순서대로 실행되는 프로그램의 실행 흐름을 제어하는 제어문입니다.

    그렇다면 이제 while문을 사용해서 아까 살펴본 코드에서 2~3번째 줄을 3번 반복한다고 해봅시다.
    이를 위해서 3번 반복했을때 조건이 false로 바뀌도록 ??? 안을 채워봅시다.

    ```jsx
    document.write('<li>1</li>');
    var i = 0;
    while (i < 3) {
    	document.write('<li>2</li>');
    	document.write('<li>3</li>');
    	i = i + 1;
    }
    document.write('<li>4</li>');
    ```

    초기 상태에서 i의 값은 0입니다.
    따라서 while 뒤의 괄호 안에 들어있는 i < 3은 true가 됩니다.
    그러면 코드가 한 번 실행됩니다. 코드가 실행되면 i = i + 1에 의해서 i의 값은 1이 됩니다.
    이 과정을 3번 반복하면 i는 3이 됩니다. 그렇게 되면 i < 3이 false가 되고, 반복문이 끝나고 마지막 줄인 document.write('<li>4</li>');가 실행됩니다.

    ### 배열과 반복문

    배열과 반복분을 결합하여 문제를 해결할 수 있습니다.

    ```jsx
    fruits = ['apple', 'banana', 'coconut'];
    ```

    이제 반복문을 이용하여 여기에 있는 값들을 하나씩 꺼내서 HTML 리스트로 나타내려고 합니다.
    여기에 있는 모든 원소들을 write하기 위해서는 3번의 반복이 필요합니다.
    그러므로 3번 반복할 수 있는 while문을 만들었습니다.

    ```jsx
    <ul>
    	<script>
    		var i = 0;
    		while (i < 3) {
    			document.write('<li></li>');
    			i = i + 1;
    		}
    	</script>
    </ul>
    ```

    그럼 이제 <li> 태그 사이에 각각의 원소를 넣습니다.
    이때 i라는 변수의 값이 0부터 2까지 1씩 증가하기 때문에, i의 값을 잘 활용하면 배열에서 원소를 순서대로 하나씩 꺼낼 수 있습니다.

    ```jsx
    <ul>
    	<script>
    		var i = 0;
    		while (i < 3) {
    			document.write('<li>'+fruits[i]+'</li>');
    			i = i + 1;
    		}
    	</script>
    </ul>
    ```

    하지만 여기에서 우리가 fruits라는 배열 안에 'durian'이라는 원소를 하나 더 추가했을 경우에는 이 반복문은 4번 실행되어야 끝까지 출력할 수 있습니다.
    하지만 지금은 3번 반복되도록 설정되어 있기 때문에 durian이 출력되지 않습니다.
    배열의 값이 추가 될때마다 반복문의 반복 횟수를 변경해주어야 하는 번거로움이 생깁니다.

    ```jsx
    fruits.push('durian');
    ```

    이를 해결하기 위해서는 반복문의 조건에 반복 횟수를 배열의 길이로 변경해주면 배열에 원소가 추가되거나 삭제되어도 자동으로 반복 횟수가 조정됩니다.

    ```jsx
    <ul>
    	<script>
    		var i = 0;
    		while (i < fruits.length) {
    			document.write('<li>'+fruits[i]+'</li>');
    			i = i + 1;
    		}
    	</script>
    </ul>
    ```

    정리하자면, 배열을 사용하면 순서대로 연관된 데이터를 저장할 수 있고, 반복문을 사용하면 순서대로 이 배열의 원소를 하나씩 꺼내서 처리할 수 있기 때문에 이 둘을 함께 사용하여 해결할 수 있는 문제들이 많습니다. 

    ### 배열과 반복문의 활용

    배열과 반복문을 이용하여 HTML과 함께 활용하는 방법을 살펴봅니다.
    이전에 조건문에서 활용했던 웹 페이지의 light/dark 모드 전환 기능에서 하이퍼링크의 색상이 모드에 따라서 변경되도록하는 예제를 만듭니다.

    먼저 해당 페이지에 있는 모든 `<a>` 태그를 가져와야 합니다.
    이전에 사용하던 querySelector라는 함수는 하나의 태그만을 가져오기 때문에 해당하는 모든 태그를 가져오기 위해서는 querySelectorAll이라는 함수를 사용해야 합니다.

    ```jsx
    var anchorList = document.querySelectorAll('a');
    ```

    이렇게 하면 querySelectorAll 함수가 찾은 모든 `<a>` 태그를 배열의 형태로 anchorList에 저장하게 됩니다.

    그렇다면 이제 이렇게 만든 배열을 반복문을 사용해서 각각의 태그에 스타일을 지정해줍니다.

    ```jsx
    <script>
    	var anchorList = document.querySelectorAll('a');
    	var i = 0;
    	while (i < anchorList.length) {
    		anchorList[i].style.color = 'blueviolet';
    		i = i + 1;
    	}
    </script>
    ```

    해당 코드를 실행하면 문서 안의 모든 `<a>` 태그들의 색상이 blueviolet으로 변경되는 것을 확인할 수 있습니다.
    이렇게 완성된 코드를 각각의 조건에 맞게 넣어주면 됩니다.