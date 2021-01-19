# JavaScript 이해하기

- JavaScript 소개

    ### WEB과 JavaScript, HTML

    WEB이 처음 등장했을 때, 사람들은 HTML을 사용해서 정보를 주고받았습니다.
    하지만 HTML은 정적입니다. 한 번 출력되면 그 모양이 바뀌지 않습니다.
    사용자와 동적으로 상호작용하는 WEB을 만들기 위해서 JavaScript가 등장했습니다.

    이제 우리는 HTML을 이용해 웹페이지를 만들고, JavaScript를 이용해 사용자와 상호작용할 수 있도록 추가할 겁니다.
    즉, 정적인 정보인 HTML을 JavaScript가 동적으로 만들어 주는 것입니다.

- JavaScript의 역할

    ### JavaScript의 역할

    JavaScript의 가장 중요한 역할은 사용자와 상호작용 할 수 있게 하는 것입니다.
    예를 들어, 웹페이지에 day/night 버튼이 존재하고 사용자가 버튼을 누를때마다 페이지가 라이트/다크 모드로 변하는 웹 페이지가 있다고 생각해 봅시다.
    어떻게 이러한 기능이 가능한 것일까요?

    ```jsx
    <!DOCTYPE html>
    <html lang="ko">
    	<head>
    		<meta charset="UTF-8">
    		<title>JavaScript 이해하기</title>
    	</head>
    	<body>
    		<h1>Hello, JavaScript</h1>
    		<input type="button" value="day" onclick="
    			document.querySelector('body').style.backgroundColor='white';
    			document.querySelector('body').style.color='black';
    			">
    		<input type="button" value="night" onclick="
    			document.querySelector('body').style.backgroundColor='black';
    			document.querySelector('body').style.color='white';
    			">
    	</body>
    </html>
    ```

    해당 페이지를 Chrom에서 개발자모드를 통해 무슨일이 일어나는지 확인해봅니다.
    day/night 버튼을 누를때마다 body 태그의 style 속성의 값이 바뀌는 것을 볼 수 있습니다.

    input 태그를 살펴보면 onclick이라는 속성이 있고 이곳에 javascript가 들어가게 됩니다.
    즉, 이 버튼을 누르면 이 javascript 코드가 실행되는 것입니다.

    ```jsx
    document.querySelector('body').style.backGroundColor='black';
    document.querySelector('body').style.color='white';
    ```

    이 코드를 쉽게 풀어보자면, 먼저 문서(document)에서 body라는 태그를 선택(selector)합니다.
    그리고 난 다음 style 속성 값에서 backgroundColor를 'black'으로, color를 'white'로 설정한다는 뜻입니다.

    ### 정리하기

    JavaScript는 사용자와 상호작용 하는 언어입니다.
    위의 예제를 통해 어떻게 이러한 일이 가능한지를 살펴보았습니다.
    웹브라우저는 한 번 출력되면 바뀔 수 없지만, JavaScript 코드에 따라서 style 속성이 추가되면서 디자인이 바뀌는 것을 확인했습니다.
    이러한 JavaScript의 특성을 이용해서 우리는 웹페이지를 더 동적으로 만들수 있습니다.

    ---

    ### 참고자료

    [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

    [JavaScript Tutorial](https://www.w3schools.com/js/default.asp)

    [JavaScript Introduction](https://www.w3schools.com/js/js_intro.asp)

    [https://www.w3schools.com/js/js_whereto.asp](https://www.w3schools.com/js/js_whereto.asp)