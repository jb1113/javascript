# JavaScript 함수

### 함수란?

함수란 무엇일까요?
수학에서 배우는 함수와 다르게 프로그래밍에서 사용하는 함수는 어떤 의미일까요?
그리고 프로그래밍에서 함수를 사용하는 이유는 무엇일까요?

### 함수

이전 반복문에서 만들었던 light/dark 모드 전환 예제에서 `<input>` 태그 안에 아주 긴 JavaScript 코드가 있었습니다.
만약 이러한 토글을 여러 개 복사해서 만든다면 코드가 아주 길어질 것입니다.
그뿐만 아니라 만약 약간의 수정을 하고 싶다고 한다면 복사된 모든 `<input>` 태그를 찾아서 하나하나 수정해 주어야 합니다.

이때 사용하는 것이 바로 함수입니다.
다음과 같이 `<head>` 태그 안에 `<script>` 태그를 만들어서 사용할 수 있습니다.

```jsx
<head>
	<script>
		function lightAndDarkHandler(self) {
			// 반복되는 아주 긴 JavaScript 코드를 여기에 넣습니다.
		}
	</script>
</head>
```

이렇게 쓰면 아주 긴 코드에 lightAndDarkHandler라는 이름을 붙여주는 것입니다.
그리고 이러한 기능을 함수, 영어로는 function이라고 부르는데 이 부분을 함수로 쓰겠다는 의미를 담아서 앞에 function이라는 키워드를 붙여줍니다.

그럼 이제 이렇게 새로운 이름을 붙여 주었으니, `<input>` 태그의 onclick 안에는 이 긴 코드를 다시 쓸 필요 없이 붙여준 이름을 써 주기만하면 됩니다.

```jsx
<input type="button" value="light" id="toggle" onclick="lightAndDarkHandler(this);">
```

### 함수의 장점

이렇게 코드를 함수로 만들게 되면 어떠한 장점들이 있을까요?
먼저 코드의 유지보수가 쉬워집니다. 하나의 함수를 여러군데에서 사용할때 이를 하나하나 바꿔줄 필요 없이 함수를 만들어 준 곳에서만 바꿔주면 됩니다.

또한 코드의 길이가 짧아집니다. 같은 코드가 계속해서 반복되는 것을 딱 한 번만 써줌으로 인해서 웹페이지의 크기를 줄여줄 수 있고 전송할 때 훨씬 유리합니다.

마지막으로 같은 함수를 사용하면 두 코드가 논리적으로 같다는 것을 한 번에 알 수 있고, 적절한 이름을 붙여주면 이 코드가 어떤 일을 하는지 한눈에 알 수 있다는 장점도 있습니다.

### 반복문으로 처리할 수 없는 상황에서 함수가 유용하게 쓰이는 예시

반복문도 반복되는 코드를 줄여줄 수 있습니다.
그렇다면 우리는 왜 반복문이 아닌 함수를 배워야 하는 걸까요?
반복문으로 처리할 수 없는 상황에서 함수가 유용하게 쓰이는 예시를 알아봅시다.

같은 코드가 반복될때, 우리는 반복문을 사용해서 이를 해결하는 방법에 대해서 배웠습니다.
하지만 다음과 같은 상황에서는 어떨까요?

```jsx
<script>
	document.write('1');
	document.write('2');
	document.write('3');
	document.write('4');
	document.write('2');
	document.write('3');
</script>
```

2를 쓰는 코드와 3을 쓰는 코드가 두 번 반복됨에도 불구하고, 그 둘 사이에 4를 쓰는 코드가 존재하기 때문에 반복문을 쓰기가 어려워집니다.
이럴때 사용하는 것이 바로 함수입니다.

### 함수의 기본 문법

반복되는 코드를 가지고 함수를 만들어 봅시다.

```jsx
<script>
	function two() {
		document.write('2');
		document.write('3');
	}
</script>
```

이제 이 코드에 two라는 이름을 붙여 주었으니, 이 이름을 사용하면 됩니다.
다음과 같이 쓰게되면 원래와 똑같은 기능을 하면서도 함수를 사용하여 간결하게 나타낼 수 있습니다.

```jsx
<script>
	function two() {
		document.write('2');
		document.write('3');
	}

	document.write('1');
	two();
	document.write('4');
	two();
</script>
```

이 코드를 실행하게 되면, two()를 만날때마다 위에서 정의된 two라는 함수의 코드를 실행하게 됩니다.

### 함수의 입력과 출력

함수는 자판기에 비유할 수 있습니다.
이전까지 만든 함수의 예제는 함수를 실행할 때마다 정해진 코드를 똑같이 반복해서 실행해 주었습니다. 마치 버튼이 1개만 있는 자판기와 같습니다.
때문에 항상 같은 코드를 반환해 줍니다.

하지만 상황에 따라서 약간씩 다른 코드가 실행되도록 만들어 준다면 더 다양하게 활용이 가능합니다. 그래서 이번에는 자판기의 버튼을 여러 개로 늘려보도록 하겠습니다.
원하는 코드에 대해 알려주면 이에 해당하는 적절한 코드를 반환해주는 함수입니다.
이를 입력과 출력이라고 부릅니다.

### 매개변수와 인자

함수는 입력과 출력으로 이루어져 있습니다.
이때 입력에 해당하는 것을 매개변수(Parameter)와 인자(Argument)라고 부르고, 출력에 해당하는 것을 리턴(Return)이라고 부릅니다.

```jsx
function onePlusOne() {
	document.write(1+1);
}
```

이 함수는 항상 1과 1을 더해서 출력해주는 함수입니다.
하지만 입력값을 받아서 거기에 따라서 다른 결과를 출력하도록 만들어보겠습니다.
예를 들어 sum(2, 3)을 한다면 5가 출력되고, sum(3, 4)를 한다면 7이 출력됩니다.

```jsx
function sum(left, right) {
	document.write(left + right);
}

sum(2, 3); // 5
sum(3, 4); // 7
```

이때 sum의 괄호 안에 들어오는 두 숫자를 각각 left, right라는 변수에 넣습니다.
이러한 변수를 매개변수(Parameter)라고 부릅니다.

이렇게 정의한 함수를 사용할때는 sum(2, 3); 처럼 사용할 수 있습니다.
이때 sum의 괄호 안에 넣어서 함수로 전달해 주는 숫자 2, 3을 인자(Argument)라고 부릅니다.

### 리턴

콘솔에 1+1을 치고 엔터를 치면 2가 나오게 됩니다.
이때 1+1은 2의 표현식이라고 부릅니다.

이전에 구현한 sum 함수를 다시 한번 살펴봅시다.

```jsx
function sum(left, right) {
	document.write(left + right);
}
```

이 sum 함수를 실행시키면 document.write를 사용해 화면에 바로 출력을 했습니다.
하지만 만약에 출력 결과는 빨간 색상으로 만들어주는 작업이 필요하다고 하면 어떻게 해야 할까요?
sumColorRed라는 새로운 함수를 만들어서 빨간색으로 write해주는 작업을 진행해 주어야 합니다.
이렇게 하면 필요할 때마다 함수를 계속해서 새로 만들어 주어야 하기 때문에 굉장히 비효율적이게 됩니다.
그렇기 때문에 이 함수를 변경하여 계산한 값의 표현식으로 만들도록 합니다.
콘솔에 1+1을 치면 2가 나오는 것처럼 말이죠.

sum이라는 함수를 여러 버전으로 만들지 않고 다음과 같이 사용하고 싶은 것입니다.

```jsx
document.write(sum(2,3)+'<br>');
document.write('<div style="color: red">'+sum(2,3)+'</div>');
```

sum 자체가 어떤 write를 수행하는 것이 아닌, 적절한 값을 돌려주는 것입니다.
이를 위해서는 리턴을 사용해서 다음과 같이 만들어 줍니다.

```jsx
function sum(left, right) {
	return left + right;
}
```

이렇게 하면 sum 함수를 통해서 결과 값만을 받게 됩니다.

### 함수의 활용

지금까지 배운 함수를 활용하여 light/dark 모드 전환 예제 코드를 더욱 효율적으로 바꾸어 봅시다.
함수는 코드 리팩토링을 할 때 자주 사용하는 방법 중 하나입니다.

먼저 버튼에 사용되는 JavaScript 코드를 함수로 만들어서 따로 저장해줍니다.
함수의 이름은 lightAndDarkHandler라고 지어줍니다.
그리고 이 함수를 `<input>` 태그의 onclick 안에 넣어줍니다.

```jsx
<script>
	function lightAndDarkHandler() {
		var target = document.querySelector('body');
		if(this.value === 'dark') {
		target.style.backgroundColor = 'black';
		target.style.color = 'white';
		this.value = 'light';
	
		var anchorList = document.querySelectorAll('a');
		var i = 0;
		while (i < anchorList.length) {
			anchorList[i].style.color = 'deepskyblue';
			i = i + 1;
		}
	} else {
		target.style.backgroundColor = 'white';
		target.style.color = 'black';
		this.value = 'dark';

			var anchorList = document.querySelectorAll('a');
			var i = 0;
			while (i < anchorList.length) {
				anchorList[i].style.color = 'crimson';
				i = i + 1;
			}
		}
	}
</script>

...
<input type="button" value="dark" onclick="lightAndDArkHandler();">
```

하지만 이 상태로 코드를 실행해보면 정상적으로 작동하지 않는 것을 볼 수 있습니다.
이유가 무엇일까요?

바로 코드 내에 포함되어 있는 this 때문입니다.
this는 그 코드가 포함되어 있는 태그를 가리키는데, 지금은 this가 정상적으로 버튼을 가리키지 못하고 있기 때문입니다.

이를 어떻게 해결할 수 있을까요?
바로 우리가 배운 매개변수와 인자를 활용하면 됩니다.
lightAndDarkHandler 함수를 사용할때 this를 사용해서 태그를 전달해주고,
lightAndDarkHandler 함수에서는 이를 매개변수로 받아서 사용하는 것입니다.

그러면 다음과 같이 코드를 작성할 수 있습니다.

```jsx
<script>
	function lightAndDarkHandler(self) {
		var target = document.querySelector('body');
		if(self.value === 'dark') {
		target.style.backgroundColor = 'black';
		target.style.color = 'white';
		self.value = 'light';
	
		var anchorList = document.querySelectorAll('a');
		var i = 0;
		while (i < anchorList.length) {
			anchorList[i].style.color = 'deepskyblue';
			i = i + 1;
		}
	} else {
		target.style.backgroundColor = 'white';
		target.style.color = 'black';
		self.value = 'dark';

			var anchorList = document.querySelectorAll('a');
			var i = 0;
			while (i < anchorList.length) {
				anchorList[i].style.color = 'crimson';
				i = i + 1;
			}
		}
	}
</script>

...
<input type="button" value="dark" onclick="lightAndDArkHandler(this);">
```

함수가 호출되는 버튼에서는 this를 인자로 넘겨주고, 함수에서는 this를 self라는 매개변수에 받아와서 이를 사용합니다.

---

### 실습 코드

```jsx
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="UTF-8">
		<title>JavaScript function</title>
		<script>
			function lightAndDarkHandler(self) {
				var target = document.querySelector('body');
				if(self.value === 'dark') {
					target.style.backgroundColor = 'black';
					target.style.color = 'white';
					self.value = 'light';
	
					var anchorList = document.querySelectorAll('a');
					var i = 0;
					while (i < anchorList.length) {
						anchorList[i].style.color = 'deepskyblue';
						i = i + 1;
					}
				} else {
					target.style.backgroundColor = 'white';
					target.style.color = 'black';
					self.value = 'dark';

					var anchorList = document.querySelectorAll('a');
					var i = 0;
					while (i < anchorList.length) {
						anchorList[i].style.color = 'crimson';
						i = i + 1;
					}
				}
			}
		</script>
	</head>
	<body>
		<h1><a href="<https://google.com>">Google</a></h1>
		<input type="button" value="dark" onclick="lightAndDarkHandler(this);">
		<ul>
			<li><a href="<https://namu.wiki/w/HTML>">HTML</a></li>
			<li><a href="<https://namu.wiki/w/CSS>">CSS</a></li>
			<li><a href="<https://namu.wiki/w/JavaScript>">JavaScript</a></li>
		</ul>
		<h2>Lorem ipsum</h2>
		<p>
			Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Ipsam aspernatur vitae sapiente laudantium velit quo unde cupiditate autem, 
			harum eaque natus perferendis ducimus saepe libero, voluptatibus voluptates possimus.
			Adipisci, delectus.
		</p>
	</body>
</html>
```

---

### 참고자료

[Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

[Function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function)

[JavaScript Functions](https://www.w3schools.com/js/js_functions.asp)