# HTML과 JS의 만남

- script 태그

    동적인 WEB을 구성하기 위해서는 HTML과 JavaScript를 함께 사용해야 합니다.
    그렇다면 서로 다른 두 언어를 어떻게 함께 사용할 수 있을까요?
    이를 위해서 필요한 것이 `<script>` 태그입니다.

    ### script 태그

    HTML의 태그 중 하나인 `<script>` 태그 안에는 JavaScript 코드를 쓸 수 있습니다.

    ```jsx
    <body>
    	<script>
    		document.write('hello, javascript!');
    	</script>
    </body>
    ```

    위와 같은 코드를 `<body>` 태그 안에 넣어서 웹페이지를 띄워보면 페이지에 hello, javascript! 라는 글자가 뜨는 것을 확인할 수 있습니다.
    하지만, 이러한 기능은 다음과 같이 HTML만 사용해서 구현할 수도 있습니다.

    ```jsx
    <body>
    	hello, javascript!
    </body>
    ```

    그렇다면 이 둘의 차이점은 무엇일까요?

    바로 JavaScript로 작성한 코드는 동적이라는 것입니다.
    만약 hello, javascript! 대신 1+1을 출력하는 경우를 확인해 봅시다.
    이때는 HTML과 JavaScript로 작성한 코드의 결과가 아래와 같이 달라집니다.

    ```
    JavaScript
    2
    HTML
    1+1
    ```

    즉, HTML로 작성한 코드는 정적이기 때문에 문자 그대로를 출력하지만 JavaScript로 작성한 코드는 동적으로 이를 계산할 수도 있다는 것입니다.

    ---

    ### 참고자료

    [JavaScript Output](https://www.w3schools.com/js/js_output.asp)

- 이벤트

    사용자와 상호작용하는 웹 사이트를 만들기 위해서는 사용자의 동작을 감지할 수 있어야 합니다.
    JavaScript에서는 이러한 사건들을 이벤트(Event)라는 이름으로 부릅니다.

    ### JavaScript와 사용자의 상호작용, 이벤트(Event)

    JavaScript에서는 다음과 같은 코드를 통해 경고창을 만들수 있습니다.

    ```
    alert('click');
    ```

    그렇다면 이제 사용자가 어떤 버튼을 눌렀을때 이 alert창이 뜨도록 만들어보겠습니다.
    먼저 빈 화면에 버튼을 만들고 이 버튼을 눌렀을 때 어떤 동작이 실행되도록 지정하는 속성인 onclick 속성에 해당하는 동작의 javascript 코드를 넣습니다.

    ```jsx
    <body>
    	<input type="button" value="버튼" onclick="alert('click');">
    </body>
    ```

    이렇게 하면 해당 버튼을 눌렀을때 경고창이 뜨게 됩니다.
    그렇다면 어떻게 이러한 일이 가능한 것인지 onclick 속성에 대해서 알아보겠습니다.

    ### Onclick 속성

    HTML 태그 안에서 onclick 속성은 JavaScript 코드를 가지게 됩니다.
    그리고 onclick이 포함된 태그가 클릭 되었을때 이 JavaScript 코드에 따라서 웹 브라우저가 동작합니다.
    위의 예제의 경우 웹 브라우저는 alert('click') 코드를 기억하고 있다가 사용자가 클릭하면 이를 실행해주는 것입니다.

    이렇게 웹 브라우저에서 일어나는 유용한 사건을 이벤트(Event)라고 합니다.

    ### 이벤트(Event)

    웹 브라우저에서 일어나는 사건을 이벤트라고 한다면 이벤트에는 어떤 종류가 있을까요?
    첫 번째로는 방금까지 살펴봤던 onclick 이벤트 입니다.
    사용자가 어떠한 것을 클릭하는 사건을 의미합니다.

    두번째는 onchange 입니다.
    예를 들면 input 태그의 type이 text인 경우처럼 입력창에 사용자가 키보드를 이용하여 무언가 입력하면 그에 따라 내용이 바뀌는 사건을 의미합니다.
    이때, 입력창에 입력한 후 입력창 바깥쪽을 클릭했을 때를 기준으로 그 전과 내용이 바뀌었는지 확인한다는 점도 알아두어야 합니다.

    이 외에도 총 10~20가지 정도의 이벤트가 존재합니다.
    이를 이용하여 사용자와 상호작용하는 웹 사이트를 만들수 있게 됩니다.

    ---

    ### 참고자료

    [JavaScript Events](https://www.w3schools.com/js/js_events.asp)

- 콘솔

    기존에는 JavaScript 코드를 작성하고 해당 코드가 작동하는지 확인하기 위해서 파일을 만들고 이를 웹사이트로 만들었어야 했습니다.
    이렇게 복잡한 과정을 거치지 않고 쉽게 JavaScript 코드를 실행시키기 위해 콘솔(Console)을 사용합니다.
    콘솔을 통해 간단한 JavaScript 코드를 실행 시킬수 있습니다.

    ### 콘솔(Console)

    웹 브라우저에서 개발자모드(F12) 또는 마우스 오른쪽 버튼 → 검사 를 누르면 뜨는 창을 통해 Console이라는 탭을 이용하면 파일을 생성하지 않고도 바로 JavaScript 코드를 실행할 수 있습니다.

    예를 들어 어떤 문자열의 길이를 알고싶은 경우에는 콘솔창을 통해 다음과 같이 어떤 문자열의 길이를 구할수 있습니다.

    ```jsx
    alert('Lorem ipsum dolor sit amet consectetur adipisicing elit.'.length);
    ```

    중요한 것은 **콘솔을 통해서 입력된 JavaScript 코드는 현재 페이지에 삽입되어 있는 JavaScript 코드 인것처럼 동작**합니다.