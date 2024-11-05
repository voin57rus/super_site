# super_site

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" href="style.css">
	<title>Document</title>
</head>
<body>
	<div class="container">
		<div class="inner">
			<div class="item">
				<img src="1.png" alt="" class="img">
				<button class="btn" id="btn1">Add</button>
			</div>
			<div class="item">
				<img src="2.png" alt="" class="img">
				<button class="btn" id="btn2">Создать пример</button>
			</div>
			<div class="item">
				<img src="3.png" alt="" class="img">
				<button class="btn" id="btn3">Add</button>
			</div>
			<div class="item">
				<img src="1.png" alt="" class="img">
				<button class="btn" id="btn4">Add</button>
			</div>
		</div>
	</div>
	<div class="usercard" id="usercard"></div>

	<script src="https://telegram.org/js/telegram-web-app.js"></script>
	<script>
		let tg = window.Telegram.WebApp;

		tg.expand();

		tg.MainButton.textColor = '#FFFFFF';
		tg.MainButton.color = '#2cab37';

		let item = "";

		// Получаем кнопки
		let btn1 = document.getElementById("btn1");
		let btn2 = document.getElementById("btn2");
		let btn3 = document.getElementById("btn3");
		let btn4 = document.getElementById("btn4");

		// Обработчики для кнопок
		btn1.addEventListener("click", function(){
			showContent("Вы выбрали товар 1", "https://example.com/item1");
		});

		btn2.addEventListener("click", function(){
			window.location.href = 'https://contributor.pw/post/why-you-should-create-an-example/';
		});

		btn3.addEventListener("click", function(){
			showContent("Вы выбрали товар 3", "https://habr.com/ru/articles/666278/");
		});

		btn4.addEventListener("click", function(){
			showContent("Вы выбрали товар 4", "https://bombosait.ru/topic/2-altezahack-%D0%BD%D0%B0-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8/");
		});

		// Функция для отображения контента
		function showContent(text, url) {
			if (tg.MainButton.isVisible) {
				tg.MainButton.hide();
			} else {
				tg.MainButton.setText(text);
				tg.MainButton.show();

				// Нажатие MainButton открывает связанный контент
				//Telegram.WebApp.onEvent("mainButtonClicked", function(){
					//window.open(url, '_blank');
				Telegram.WebApp.onEvent("mainButtonClicked", function(){
                                     window.location.href = url; // Открывает ссылку в том же окне


				});
			}
		}

		// Получаем элемент usercard и создаем параграф
		let usercard = document.getElementById("usercard");
		let p = document.createElement("p");

		// Проверка наличия данных пользователя
		if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
			const { first_name, last_name, id } = tg.initDataUnsafe.user;
			p.innerText = `${first_name} ${last_name}\nВаш ID: ${id}`;
		} else {
			p.innerText = "Данные пользователя не найдены.";
		}

		usercard.appendChild(p);

		// Обработчик клика для btn2, открывающий ссылку
		btn2.addEventListener('click', () => {
			window.location.href = 'https://contributor.pw/post/why-you-should-create-an-example/';
		});
	</script>
	<script src="app.js"></script>
</body>
</html>
