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

- 프로그램, 프로그래밍, 프로그래머

    프로그래밍이란 무엇일까요? 그리고 프로그램이라는 관점에서 JavaScript와 HTML은 어떤 차이가 있을까요?

    ### JavaScript란 무엇인가?

    HTML과 JavaScript는 모두 컴퓨터 언어입니다.
    하지만 HTML과는 달리 JavaScript는 컴퓨터 프로그래밍 언어이기도 합니다.
    그렇다면 여기에서 프로그램이란 무엇일까요?

    ### 프로그램, 프로그래밍, 프로그래머

    프로그램에는 순서라는 의미가 있습니다.
    프로그래밍은 이러한 순서를 만드는 행위를 말합니다.
    프로그래머는 이러한 순서를 만드는 일을 하는 사람을 의미합니다.
    이러한 용어는 소프트웨어 분야 뿐만 아니라 다양한 분야에서도 사용되는 말입니다.

    컴퓨터를 사용할 때에는 다양한 기능을 순서대로 사용하게 됩니다.
    그리고 보통은 이러한 기능이 반복적으로 이용됩니다.
    컴퓨터 프로그래밍 언어란 시간의 순서에 따라서 실행되어야 할 기능을 글로 적어두는 방식을 의미합니다.
    작업이 필요할 때마다 적어둔 글을 컴퓨터가 실행하도록 건네주는 것입니다.

    ### HTML과 JavaScript의 비교

    HTML로 만든 웹페이지는 시간의 순서에 따라 실행되지 않고, 한 번 만들어지면 바뀌지 않습니다. 때문에 HTML은 컴퓨터 프로그래밍 언어가 아닙니다.

    반면에 JavaScript는 사용자와 상호작용하고, 이를 위해서 시간에 따라 여러 기능이 실행되어야 하기 때문에 프로그래밍이라는 형태를 띄게 됩니다. 따라서 JavaScript는 컴퓨터 프로그래밍 언어라고 부를 수 있습니다.

    그리고 더 나아가서 시간에 따라 코드가 실행되는 것 외에도, 조건에 따라 다른 코드가 실행되도록 하거나, 같은 코드가 반복적으로 실행할 수 있는 방법도 고안하게 된 것입니다.