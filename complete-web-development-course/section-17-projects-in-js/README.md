# Section 17: Projects in JS

---

Section ini berfokus pada implementasi materi sebelumnya (terutama materi soal DOM) menjadi sebuah *project*, mulai dari aplikasi **Todolist**, sampai **Quiz App** dengan Javascript.

Dengan mengetahui cara set data ke Local Storage : 
```javascript
localStorage.setItem('key', 'value');
```

jika value berbentuk (in this case) array,
untuk menyimpan ke localStorage perlu di "stringify" terlebih dahulu seperti ini :
```javascript
localStorage.setItem('todo_list', JSON.stringify(TODOS));
```

dan cara get data dari Local Storage : 
```javascript
localStorage.getItem('key');

// mengambil value dari item yang sudah di "stringify"
JSON.parse(localStorage.getItem('key with object value that stringified(?)'));
```
Aku belajar menyimpan data sementara di local storage browser, terutama untuk app TodoList dan Expense Tracker.

---
Selain itu ada event method(?) dari javascript yang baru aku tahu dan pelajari di section ini, wicis **Event Bubbling**✨
```javascript
taskList.querySelector('button').addEventListener('click', function (e) {
  e.stopPropagation();
  deleteTask(task);
});
```
Dengan menggunakan `e.stopPropagation()`, memungkinkan kita untuk (in this case) klik, tanpa mempengaruhi parent elementnya (cmiiw).

---
Adapun yang tidak kalah menarik yang dipelajari di section ini adalah **API Fetching** (handle any type of API).
```javascript
async function fetchWeatherData(city) {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&units=metric&appid=${API_KEY}`
  const response = await fetch(url);
  if (!response.ok) {
    throw new Error(response.statusText);
  }
  const data = await response.json();
  return data;
}
```
Adalah pertama kalinya aku membuat *Weather App*🩻 padahal katanya ini basic, tapi bisa-bisanya aku melewatkan hal ini selama belajar coding. Dengan menggunakan konsep(?) *async await* nya javascript, aku fetching API ke [Open Weather Map](https://openweathermap.org/) untuk mendapatkan data cuaca di suatu kota.

---
Dan pelajaran yang menurutku paling penting adalah, ***How to write a good code***(?). Secara tidak langsung, di section ini memperlihatkan bagaimana untuk menerapkan konsep **DRY**, dan ***Clean Code***. Dengan memisahkan setiap tugas ke fungsi-fungsi yang berbeda, agar setiap fungsi mempunyai tugas sesedikit mungkin
```javascript

function renderTask(task) {
    // first way
    // const tempHtml = `
    //     <li
    //       data-id="${task.id}"
    //       class="flex justify-between items-center text-text-light dark:text-text-dark p-2 bg-button-bg-light dark:bg-button-bg-dark rounded-sm">
    //       <span class="cursor-default">${task.task}</span>
    //       <button class="py-1 px-3 rounded-sm cursor-pointer bg-bg-light-danger dark:bg-bg-dark-danger dark:hover:bg-bg-dark-danger-hover">Delete</button>
    //     </li>
    //   `
    // taskLists.insertAdjacentHTML("beforeend", tempHtml);

    // second way
    // create 'li' element
    const taskList = document.createElement('li');

    // set data-id attribute
    taskList.setAttribute('data-id', task.id);

    // class on list item if task is completed
    if (task.completed) {
      taskList.classList.remove('bg-button-bg-light', 'dark:bg-button-bg-dark', 'text-text-light', 'dark:text-text-dark')
      taskList.classList.add('bg-button-bg-light-hover', 'dark:bg-button-bg-dark-hover', 'text-text-muted-light', 'dark:text-text-muted-dark');
    }

    // default class
    taskList.classList.add('flex', 'relative', 'justify-between', 'items-center', 'text-text-light', 'dark:text-text-dark', 'p-2', 'bg-button-bg-light', 'dark:bg-button-bg-dark', 'rounded-sm')

    // write task in list item
    taskList.innerHTML = `
      <span class="cursor-default ${task.completed && 'line-through'}">${task.task}</span>
      <button class="${task.completed && 'line-through'} py-1 px-3 rounded-sm cursor-pointer bg-bg-light-danger dark:bg-bg-dark-danger dark:hover:bg-bg-dark-danger-hover">Delete</button>
    `

    // eventListener to complete task
    taskList.addEventListener('click', function (e) {
      if (e.target.tagName === "BUTTON") return;
      completeTask(task);
    });

    // eventListener to delete task
    taskList.querySelector('button').addEventListener('click', function (e) {
      e.stopPropagation();
      deleteTask(task);
    });

    // append list item to parent
    taskLists.appendChild(taskList);
  }

function renderAllTask() {
  taskLists.innerHTML = '';
  if (tasks.length < 1) {
    taskLists.innerHTML = `
        <li
        class="text-sm text-text-muted-light dark:text-text-muted-dark">
        <span class="cursor-default">Nothing todo now. Let's add new task</span>
      </li>
    `;

    return;
  }
  tasks.forEach(task => renderTask(task));
}
```
setiap tugas tidak dibuat di fungsi yang sama, `renderTask`, `completeTask`, sampai `deleteTask` dibuat di fungsi yang berbeda. **BTW** kodingannya terlihat banyak sekali (masih harus belajar agar bisa terlihat lebih clean lagi, huhu😭😭).

---
*anw*, kurang lebih itu yang Aku dapatkan di section ini, sisanya liat langsung aja ke *source code* semua project dari section ini. [Lihat di sini](https://github.com/LIan2nd/javascript-projects-fromjournal)