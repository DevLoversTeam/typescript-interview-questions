<h1>
  TypeScript <img src="./assets/typescript.svg" width="40" height="40" />
</h1>

<h2>Найпопулярніші запитання та відповіді на співбесіді з TypeScript</h2>

<details>
<summary>1. Поясніть, що таке TypeScript та які його ключові відмінності від JavaScript.</summary>

#### TypeScript

**TypeScript** — це надбудова над JavaScript, яка додає статичну типізацію,
інтерфейси та інші можливості для підвищення надійності коду.

#### Відмінності:

- **_Типізація:_** TS має статичні типи, JS — динамічні.

- **_Розробка:_** TS виявляє помилки на етапі компіляції, JS — під час
  виконання.

- **_Сумісність:_** TS компілюється у JS, тому працює у всіх середовищах JS.

- **_Інструменти:_** краща підтримка IDE (автодоповнення, рефакторинг).

</details>

<details>
<summary>2. Що означає твердження, що TypeScript є надмножиною JavaScript?</summary>

#### TypeScript

- Це означає, що будь-який коректний JavaScript-код є також коректним
  TypeScript-кодом. TypeScript розширює можливості JS, додаючи типи та інші
  фічі, але при цьому не змінює базову мову.

</details>

<details>
<summary>3. Які основні вбудовані типи даних підтримує TypeScript?</summary>

#### TypeScript

**Основні типи в TypeScript:**

- `string` — рядки

- `number` — числа (цілі та з плаваючою крапкою)

- `boolean` — логічні значення

- `null` та `undefined`

- `any` — будь-який тип

- `unknown` — невідомий тип (безпечніша альтернатива any)

- `void` — відсутність значення (часто у функціях)

- `never` — функція ніколи не повертає значення (наприклад, кидає помилку)

- `object` — об’єкти

- `Масиви` (type[] або Array<type>)

- `Кортежі` ([type1, type2, ...])

- `enum` — перерахування

</details>

<details>
<summary>4. Які способи оголошення змінних у TypeScript та як до них застосовується типізація?</summary>

#### TypeScript

У TypeScript змінні оголошуються так само, як у JavaScript: `let`, `const`,
рідше `var`.

**Тип можна:**

- вивести автоматично (Type Inference):

```TypeScript
let age = 25; // type: number
```

- задати явно:

```TypeScript
let age: number = 25;
const name: string = "Alice";
```

Зазвичай рекомендують використовувати `const` для незмінних значень, `let` для
змінних, а явну типізацію — там, де виведення типу неочевидне.

</details>

<details>
<summary>5. Що таке інтерфейси в TypeScript і для чого вони використовуються?</summary>

#### TypeScript

Інтерфейси в TypeScript описують структуру об’єкта (його властивості та їх
типи), не створюючи конкретної реалізації. Вони допомагають забезпечити контракт
між частинами коду.

**Основні можливості:**

- Опис форми об’єкта:

```TypeScript
interface User {
  id: number;
  name: string;
  isAdmin?: boolean; // необов’язкове поле
}

const user: User = { id: 1, name: "Alice" };
```

- Підтримка опціональних властивостей (?).

- Можливість розширення (extends).

- Використання для опису структур функцій, класів та масивів.

По суті, інтерфейси — це спосіб зробити код більш передбачуваним і безпечним.

</details>

<details>
<summary>6. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>7. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>8. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>9. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>10. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>11. ???</summary>

#### TypeScript

- Coming soon...😎

</details>
