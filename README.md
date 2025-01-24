<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Курс похудения и здорового образа жизни.">
  <title>Закрытый курс похудения</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div id="access-denied">
    <h1>Доступ запрещён</h1>
    <p>Для входа необходима специальная ссылка. Если вы её получили, нажмите ниже.</p>
    <button id="enter-button">Ввести код доступа</button>
  </div>

  <div id="course-content" class="hidden">
    <header>
      <h1>Добро пожаловать в курс похудения!</h1>
      <p>Ваш гид в мире здорового питания и тренировок.</p>
    </header>
    <main>
      <section>
        <h2>Шаг 1: Разминка</h2>
        <p>Каждое утро начинайте с лёгкой 10-минутной зарядки. Видео уроки уже доступны!</p>
      </section>
      <section>
        <h2>Шаг 2: Питание</h2>
        <p>Научитесь готовить полезные и вкусные блюда. Рецепты внутри!</p>
      </section>
      <section>
        <h2>Шаг 3: Прогресс</h2>
        <p>Ведите дневник похудения и анализируйте свои успехи.</p>
      </section>
    </main>
    <footer>
      <p>Автор курса: Нурлан. Все права защищены.</p>
    </footer>
  </div>

  <script src="script.js"></script>
</body>
</html>

body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f9f9f9;
  color: #333;
}

header {
  text-align: center;
  background-color: #4CAF50;
  color: white;
  padding: 20px;
}

main {
  padding: 20px;
}

section {
  margin: 20px 0;
}

.hidden {
  display: none;
}

#access-denied {
  text-align: center;
  margin-top: 50px;
}

#enter-button {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
}

#enter-button:hover {
  background-color: #45a049;
}

const secretLink = "my-secret-link"; // Ваш уникальный код доступа
const urlParams = new URLSearchParams(window.location.search);

document.addEventListener("DOMContentLoaded", () => {
  const accessDeniedDiv = document.getElementById("access-denied");
  const courseContentDiv = document.getElementById("course-content");

  if (urlParams.get("access") === secretLink) {
    accessDeniedDiv.classList.add("hidden");
    courseContentDiv.classList.remove("hidden");
  } else {
    accessDeniedDiv.classList.remove("hidden");
    courseContentDiv.classList.add("hidden");
  }

  document.getElementById("enter-button").addEventListener("click", () => {
    alert("Получите доступ по специальной ссылке!");
  });
});
