# JavaScript 객체

지금까지는 코드가 많아질때, 이를 정리할 수 있는 방법으로서 함수를 배웠습니다.
그렇다면 이러한 함수를 계속 만들다 보면 함수가 너무 많아지는 경우도 생기게 됩니다.
이때 함수들을 정리하는 방법에는 어떤 것들이 있을까요?

### 객체

우리는 코드의 정리정돈을 위해서 함수라는 개념을 사용했습니다.
객체 또한 이러한 목적을 가지고 사용되는 방법입니다.
객체는 함수의 기반 위에서 존재하는 개념입니다.
서로 연관된 함수와 변수가 아주 많아지면 이를 정리하기 위해서 사용합니다.

JavaScript 함수에서 사용했던 light/dark 모드 예제 중 반복되는 `<a>` 태그의 색상을 바꾸어주는 부분을 함수로 만들어 줍니다.

```jsx
<script>
	function linksSetColor(color) {
		var anchorList = document.querySelectorAll('a');
		var i = 0;
		while (i < anchorList.length) {
			anchorList[i].style.color = color;
			i = i + 1;
		}
	}
</script>
```

그러면 이제 `<a>` 태그의 색상을 바꾸어 주는 부분에서 다음과 같이 사용할 수 있습니다.

```jsx
linksSetColor("deepskyblue");
```

같은 방법으로 배경과 글자의 색상을 바꾸는 코드도 따로 함수로 만들어 봅시다.
이때 함수 이름이 겹치지 않도록 주의해야 합니다.

```jsx
function bodySetColor(color) {
	document.querySelector('body').style.color = color;
}

...
bodySetColor('white');
bodySetColor('black');
```

```jsx
function bodySetBackgroundColor(color) {
	document.querySelector('body').style.backgroundColor = color;
}

...
bodySetBackgroundColor('black');
bodySetBackgroundColor('white');
```

각각을 함수로 만들면 아래와 같은 코드가 됩니다.

```jsx
<script>
	function linksSetColor(color) {
		var anchorList = document.querySelectorAll('a');
		var i = 0;
		while (i < anchorList.length) {
			anchorList[i].style.color = color;
			i = i + 1;
		}
	}

	function bodySetColor(color) {
		document.querySelector('body').style.color = color;
	}

	function bodySetBackgroundColor(color) {
		document.querySelector('body').style.backgroundColor = color;
	}

	function lightAndDarkHandler(self) {
		if(self.value === 'dark') {
			bodySetBackgroundColor('black');
			bodySetColor('white');
			self.value = 'light';

			linksSetColor("deepskyblue");
		} else {
			bodySetBackgroundColor('white');
			bodySetColor('black');
			self.value = 'dark';

			linksSetColor("crimson");
		}
	}
</script>
```

이렇게 다양한 함수들이 존재하는 상황에서 우리는 객체를 사용하면 됩니다.
예를 들어 함수의 종류가 아주 많아지게 되면 이 함수들끼리 이름이 중복되지 않도록 만들기 위해서 굉장히 복잡한 이름을 사용해야 합니다.

이때 객체를 사용하면 이 함수들을 비슷한 것들끼리 그룹으로 만들어 묶어줄 수 있습니다.
마치 컴퓨터에서 폴더를 만들어서 정리하는 것과 비슷합니다.
이렇게 나뉜 함수들은 서로 다른 그룹끼리는 이름이 겹쳐도 괜찮습니다.

우리는 JavaScript 기초에서 이미 이러한 객체를 사용해본 경험이 있습니다.
바로 아래 코드에서입니다.

```jsx
document.querySelector('body');
```

여기에서 document가 바로 객체이고, querySelector가 document라는 객체에 속해있는 함수라고 생각할 수 있습니다.
이렇게 객체에 속해있는 함수들은 메소드(Method)라는 별도의 이름으로 부르게 됩니다.

### 객체의 읽기와 쓰기

이전에 배열에 대해서 배웠습니다.
어떤 값들을 순서를 가지도록 저장하는 구조였습니다.
그렇다면 순서 없이 저장하는 구조도 필요할 것입니다. 그것이 바로 객체입니다.

객체에는 순서가 없는 대신 각각에 이름이 붙어있습니다.
이름을 이용해서 값들을 꺼내고 넣습니다.

다음은 객체를 생성하는 문법입니다.

```jsx
var coworkers = {
	"programmer": "SY",
	"designer": "JB"
}
```

객체를 생성할 때에는 배열과는 달리 중괄호( { } )를 사용합니다.
그리고 각 요소들은 각각 이름과 값으로 이루어져 있습니다.
예를 들면 SY라는 값에는 programmer라는 이름표가 붙어있는 것입니다.

그렇다면 이 요소들을 꺼낼 때에는 어떻게 해야 할까요?

```jsx
document.write(coworkers.programmer);
> "SY"
document.write(coworkers["programmer"]);
> "SY"
```

위와 같이 두가지 방법 모두 동일하게 coworkers라는 객체 안에서 programmer라는 이름을 가진 값을 가져와서 출력하게 됩니다.

다음으로 객체에 요소를 추가하는 방법입니다.

```jsx
coworkers.bookkeeper = "miho";
coworkers["bookkeeper"] = "miho";
```

위의 두가지 모두 coworkers라는 객체 안에 bookkeeper라는 이름으로 miho라는 값을 넣는 것입니다.
둘 다 같은 작업을 실행하게 됩니다.
하지만 만약에 이름에 공백이 존재한다면 첫번째 줄의 코드처럼 쓰면 오류가 나기 때문에 두번째 줄처럼 사용해야 합니다.

```jsx
coworkers.data scientist = "tami"; -> X
coworkers["data scientist"] = "tami"; -> O

document.write(coworkers["data scientist"]);
> "tami"
```

### 객체의 순회(iteration)

객체는 순서가 없는 배열이라고 배웠습니다.
배열에서는 반복문을 사용해서 모든 요소들에 차례로 접근할 수 있었습니다.
그렇다면 객체에서는 어떻게 모든 요소에 차례대로 접근할 수 있을까요?

객체에 있는 모든 값들을 가져오기 위해서 for in을 사용하여 객체의 모든 요소에 접근할 수 있습니다.

```jsx
var coworkers = {
	"programmer": "SY",
	"designer": "JB"
}

for (var key in coworkers) {
	document.write(key+'<br>');
}

> programmer
> designer
```

for in을 쓰게되면 coworkers에 있는 이름들을 하나씩 가져오게 됩니다.
그리고 이 이름을 차례대로 변수 key에 넣어줍니다.
그러면 그 key들이 차례대로 출력됩니다. 결과적으로는 programmer와 designer가 출력됩니다.

그렇다면 이름 대신 그 이름에 해당하는 값을 출력하고 싶다면 어떻게 하면 될까요?

```jsx
for (var key in coworkers) {
	document.write(coworkers[key]+'<br>');
}

> SY
> JB
```

위의 코드처럼 key를 이용하여 key에 해당하는 값을 가져오도록 만들면 됩니다.

### 프로퍼티와 메소드

객체에는 다양한 것들이 들어갈 수 있습니다.
이름과 값뿐만 아니라 객체에는 심지어 함수까지 들어갈 수 있습니다.
객체에 함수를 어떻게 넣는지 그리고 이를 어떤 방식으로 활용하는지 알아봅니다.

### 객체의 메소드

이전에 사용했던 coworkers라는 객체에 새로운 함수, 즉 메소드를 추가합니다.
바로 showAll()이라는 메소드입니다.

```jsx
coworkers.showAll = function() {
	for (var key in coworkers) {
		document.write(key+' : '+coworkers[key]+'<br>');
	}
}

// 이것은 이것과 동일한 의미를 지닙니다.
var showAll = function() {
	...
}

// 함수를 정의하는 방법과 동일합니다.
function showAll() {
	...
}
```

즉, coworkers에서만 사용할 수 있는 showAll 이라는 메소드를 추가하게 된 것입니다.

하지만 이 방법은 그렇게 좋은 방법은 아닙니다.
왜냐하면 coworkers라는 변수 이름이 바뀌면 함수를 수정해야 하기 때문입니다.
이때 사용하는 것이 이전에도 사용했었던 this 입니다.
coworkers 대신에 이 메소드가 쓰인 객체를 가리키는 this를 사용해주면 됩니다.

```jsx
coworkers.showAll = function() {
	for (var key in this) {
		document.write(key+' : '+this[key]+'<br>');
	}
}

> programmer : SY
> designer : JB
> bookkeeper : miho
> data scientist : tami
> showAll : function() { for (var key in this)
	{ document.write(key+' : '+this[key]+'<br>'); } }
// 출력결과를 보면 showAll 조차도 coworkers에 소속된 데이터이기 때문에 화면에 표시됨
```

### 객체의 프로퍼티

이렇게 객체에 해당하는 함수들은 메소드라고 부릅니다.
그리고 객체에 해당하는 변수들도 있습니다.
예를 들면 coworkers.programmer에서 programmer에 해당하는 것들입니다.
이런 변수들을 프로퍼티(property)라고 부릅니다.

### 객체의 활용

함수를 사용하여 만들었던 light/dark 모드 전환 예제에 객체를 활용하여 코드를 리팩토링 해보겠습니다.

먼저 Body라는 이름의 객체를 다음과 같이 만듭니다.

```jsx
var Body = {
	setColor: function (color) {
		document.querySelector('body').style.color = color;
	},
	setBackgroundColor: function (color) {
		document.querySelector('body').style.backgroundColor = color;
	}
}
```

객체의 각 프로퍼티들은 쉼표(,)를 이용해서 구분하기 때문에 빼먹지 않도록 주의합니다.

`<a>` 태그의 색상을 변경해주는 기능을 하는 함수에도 Links라는 객체를 만들어 줍니다.

```jsx
var Links = {
	setColor: function (color) {
		var anchorList = document.querySelectorAll('a');
		var i = 0;
		while (i < anchorList.length) {
			anchorList[i].style.color = color;
			i = i + 1;
		}
	}
}
```

이렇게 객체를 이용해 만들게 되면 Body와 Links에 모두 setColor라는 함수가 존재할 수 있습니다.
하지만 이 둘을 사용할 때에는 다음과 같이 다르게 사용합니다.

```jsx
Body.setColor('white');
Links.setColor('deepskyblue');
```

함수 이름이 같아도 다른 객체에 소속된 메소드이기 때문에 충돌이 일어나지 않습니다.

---

### 실습 코드

```jsx
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="UTF-8">
		<title>JavaScript function</title>
		<script>
			var Links = {
				setColor: function (color) {
					var anchorList = document.querySelectorAll('a');
					var i = 0;
					while (i < anchorList.length) {
						anchorList[i].style.color = color;
						i = i + 1;
					}
				}
			}

			var Body = {
				setColor: function (color) {
					document.querySelector('body').style.color = color;
				},
				setBackgroundColor: function (color) {
					document.querySelector('body').style.backgroundColor = color;
				}
			}

			function lightAndDarkHandler(self) {
				var target = document.querySelector('body');
				if(self.value === 'dark') {
					Body.setBackgroundColor('black');
					Body.setColor('white');
					self.value = 'light';

					Links.setColor('deepskyblue');
				} else {
					Body.setBackgroundColor('white');
					Body.setColor('black');
					self.value = 'dark';

					Links.setColor('crimson');
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

[Introducing JavaScript objects](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)

[JavaScript object basics](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)

[JavaScript Objects](https://www.w3schools.com/js/js_objects.asp)

[JavaScript Objects](https://www.w3schools.com/js/js_object_definition.asp)

[JavaScript Properties](https://www.w3schools.com/js/js_object_properties.asp)

[JavaScript Methods](https://www.w3schools.com/js/js_object_methods.asp)