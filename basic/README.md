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
    **JavaScript**
    2
    **HTML**
    1+1
    ```

    즉, HTML로 작성한 코드는 정적이기 때문에 문자 그대로를 출력하지만 JavaScript로 작성한 코드는 동적으로 이를 계산할 수도 있다는 것입니다.

    ---

    ### 참고자료

    [JavaScript Output](https://www.w3schools.com/js/js_output.asp)