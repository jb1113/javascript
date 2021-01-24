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