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
////////////////////////

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
            <img src="1.jpg" alt="" class="img">
            <button class="btn" id="btn1">Пример</button>
        </div>
        <div class="usercard" id="usercard"></div> <!-- Элемент usercard перемещен ниже -->
    </div>
</div>

			
		    </div>
			
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
		
		// Обработчики для кнопок
		btn1.addEventListener("click", function(){
			showContent("смотри содержимое страницы", "https://contributor.pw/post/why-you-should-create-an-example/");
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

		// Получаем элемент usercard и создаем три параграфа
let usercard = document.getElementById("usercard");
let p1 = document.createElement("p"); // Для текста "Привет, бро!"
let p2 = document.createElement("p"); // Для приветствия
let p3 = document.createElement("p"); // Для ID

// Добавляем текст любой
p1.innerText = "🤖";

// Проверка наличия данных пользователя
if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
    const { first_name, last_name, id } = tg.initDataUnsafe.user;
    p2.innerText = `Приветствую тебя, ${first_name} ${last_name}`;  // Приветствие
    p3.innerText = `Ваш ID: ${id}`;  // ID на новой строке
} else {
    p2.innerText = "Данные пользователя не найдены.";  // Если данных нет
    p3.innerText = "";  // Если данных нет, ID не показываем
}

// Добавляем параграфы в usercard
usercard.appendChild(p1); // Добавляем текст любой
usercard.appendChild(p2); // Добавляем приветствие
usercard.appendChild(p3); // Добавляем ID

// Обработчик клика для btn1, открывающий ссылку
btn1.addEventListener('click', () => {
    window.location.href = 'https://contributor.pw/post/why-you-should-create-an-example/';
});

	</script>
	<script src="app.js"></script>
</body>
</html>

/////////////////

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
            	<img src="1.jpg" alt="" class="img">
            	<button class="btn" id="btn1">Смотреть</button>
        	</div>
        	<div class="usercard" id="usercard"></div>
    	</div>
	</div>

	<script src="https://telegram.org/js/telegram-web-app.js"></script>
	<script>
		let tg = window.Telegram.WebApp;

		tg.expand();

		tg.MainButton.textColor = '#FFFFFF';
		tg.MainButton.color = '#2cab37';

		let item = "";
		let btn1 = document.getElementById("btn1");

		btn1.addEventListener("click", function() {
			//showContent("Смотри как создать пример", "https://contributor.pw/post/why-you-should-create-an-example/");
			//showContent("Смотри как создать пример", "https://voin57rus.github.io/video.mp4");
		
			showContent("Смотри как создать пример", "https://drive.google.com/file/d/1r1uVs7uE6ksm0QIJ_FnyB82HDmZbhg1P/view?usp=drive_link");
		});

		function showContent(text, url) {
			if (tg.MainButton.isVisible) {
				tg.MainButton.hide();
			} else {
				tg.MainButton.setText(text);
				tg.MainButton.show();

				// Добавляем один обработчик события mainButtonClicked
				//Telegram.WebApp.onEvent("mainButtonClicked", function() {
					//window.open(url, '_blank'); // Откроет ссылку в новом окне
				//а этот в нутри 
				Telegram.WebApp.onEvent("mainButtonClicked", function(){
                                     window.location.href = url; // Открывает ссылку в том же окне
				});
			}
		}

		// Создаем элементы usercard
		let usercard = document.getElementById("usercard");
		let p1 = document.createElement("p");
		let p2 = document.createElement("p");
		let p3 = document.createElement("p");

		p1.innerText = "🤖";

		// Проверка данных пользователя
		if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
			const { first_name, last_name, id } = tg.initDataUnsafe.user;
			p2.innerText = `Приветствую тебя, ${first_name} ${last_name}`;
			p3.innerText = `Ваш ID: ${id}`;
		} else {
			p2.innerText = "Данные пользователя не найдены.";
			p3.innerText = "";
		}

		// Добавляем параграфы в usercard
		usercard.appendChild(p1);
		usercard.appendChild(p2);
		usercard.appendChild(p3);
	</script>
	<script src="app.js"></script>
</body>
</html>
//для него стиль 
/*
body {
    margin: 0;
    padding: 0;
    font-size: 18px;
    color: var(--tg-theme-text-color);
    background: var(--tg-theme-bg-color);
}

.container {
    width: 100%;
    height: calc(20vh - 567px); /* Уменьшаем высоту на 567px (~15 см) */
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.inner {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    height: 100%;
}

.img {
    width: 100%;
    height: 50%;
    object-fit: cover;
}

.item {
    text-align: center;
    width: 100%;
}

.btn {
    display: block;
    width: 100%;
    padding: 10px 20px;
    border: none;
    background: rgb(248, 168, 24);
    border-radius: 10px;
    color: #fff;
    text-transform: uppercase;
    font-weight: 700;
    transition: background .2s linear;
}

.btn:hover {
    background: #2cab37;
}

.usercard {
    text-align: center;
    margin-top: 10px; /* Добавляем отступ сверху для элемента с информацией */
}

*/
//////////////////////////////////////////////////////////////////////
//
последняя версия ее ставить
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Document</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-size: 18px;
            color: var(--tg-theme-text-color); /* Текст адаптируется под тему Telegram */
            background: var(--tg-theme-bg-color); /* Фон адаптируется под тему Telegram */
        }

        /* Контейнер */
        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            gap: 20px; /* Отступы между элементами */
            margin-top: 20px;
            width: 100%; /* Контейнер занимает всю ширину */
        }

        /* Внутренний контейнер */
        .inner {
            display: flex;
            flex-direction: column; /* Вертикальное расположение */
            gap: 20px; /* Отступы между элементами */
            align-items: center;
            width: 100%; /* Вся ширина */
        }

        /* Элемент с изображением и кнопками */
        .item {
            display: flex;
            flex-direction: column; /* Вертикальное расположение */
            justify-content: center;
            align-items: center;
            gap: 10px; /* Отступы между изображением и кнопками */
            width: 100%; /* Контейнер занимает всю ширину */
        }

        /* Изображение */
        .img {
            width: 100%; /* Занимает всю ширину */
            max-width: 400px; /* Максимальная ширина */
            height: auto; /* Автоматическая высота */
            border-radius: 8px; /* Скругленные углы */
        }

        /* Кнопки */
        btn {
			padding: 10px 20px;
			background-color: #2cab37;
			color: #fff;
			border: none;
			cursor: pointer;
			font-size: 14px;
			border-radius: 2px;
		}


        
        /* Стили для карточки пользователя */
         .usercard {
            text-align: center;
            margin-top: 10px;
            padding: 20px;
            background: var(--tg-theme-bg-color); /* Фон адаптируется под тему Telegram */
            color: var(--tg-theme-text-color); /* Цвет текста */
          //  border-radius: 8px; /* Скругленные углы */
         //   max-width: 300px; /* Максимальная ширина */
           // box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3); /* Легкая тень */
        }
	    
    </style>
</head>
<body>
    <div class="container">
        <div class="inner">
            <div class="item">
                <img src="1.jpg" alt="Example Image" class="img">
                <button class="btn" id="btn1">Небольшой гайд как сделать пример</button>
                <button class="btn" id="btn2">Смотри почему стоит создать пример</button>
            </div>
            <div class="usercard" id="usercard"></div>
        </div>
    </div>

    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <script>
        let tg = window.Telegram.WebApp;

        tg.expand();
        tg.MainButton.textColor = '#FFFFFF';
        tg.MainButton.color = '#2cab37';

        // Получаем кнопки
        let btn1 = document.getElementById("btn1");
        let btn2 = document.getElementById("btn2");

        // Обработчик для первой кнопки
        btn1.addEventListener("click", function () {
          showContent("Смотри гайд как создать пример", "https://video-mp4-pied.vercel.app/video.mp4");
		//https://voin57rus.github.io/video.mp4/
		// showContent("Смотри как создать пример", ""https://drive.google.com/file/d/1r1uVs7uE6ksm0QIJ_FnyB82HDmZbhg1P/view?usp=drive_link");
        });

        // Обработчик для второй кнопки
        btn2.addEventListener("click", function () {
          //  showContent("Смотри другой пример", "https://voin57rus.github.io/video.mp4");
		 showContent("Смотри почему стоит создать пример", "https://contributor.pw/post/why-you-should-create-an-example");
		
        });

        // Функция для отображения контента
        function showContent(text, url) {
            if (tg.MainButton.isVisible) {
                tg.MainButton.hide();
            } else {
                tg.MainButton.setText(text);
                tg.MainButton.show();

                // Нажатие MainButton открывает связанный контент
                Telegram.WebApp.onEvent("mainButtonClicked", function () {
                    window.location.href = url;
                });
            }
        }

        // Создаем элементы usercard
        let usercard = document.getElementById("usercard");
        let p1 = document.createElement("p");
        let p2 = document.createElement("p");
        let p3 = document.createElement("p");

        p1.innerText = "🤖";

        // Проверка данных пользователя
        if (tg.initDataUnsafe && tg.initDataUnsafe.user) {
            const { first_name, last_name, id } = tg.initDataUnsafe.user;
            p2.innerText = `Приветствую тебя, ${first_name} ${last_name}`;
            p3.innerText = `Ваш ID: ${id}`;
        } else {
            p2.innerText = "Данные пользователя не найдены.";
            p3.innerText = "";
        }

        // Добавляем параграфы в usercard
        usercard.appendChild(p1);
        usercard.appendChild(p2);
        usercard.appendChild(p3);
    </script>
</body>
</html>


