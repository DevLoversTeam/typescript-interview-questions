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
<summary>6. Що таке enum у TypeScript та в яких випадках його доцільно використовувати?</summary>

#### TypeScript

- `enum` (перерахування) — це тип, який дозволяє задати набір іменованих
  констант.

#### Види:

- **Numeric enum** (значення автоматично інкрементуються):

```TypeScript
enum Direction {
  Up,    // 0
  Down,  // 1
  Left,  // 2
  Right  // 3
}
```

- **String enum:**

```TypeScript
enum Role {
  Admin = "ADMIN",
  User = "USER",
  Guest = "GUEST"
}
```

Використовується, коли є обмежений набір варіантів (напр. ролі користувачів,
статуси замовлення, напрямки руху). Це робить код більш читабельним і безпечним,
ніж "магічні числа" чи рядки.

</details>

<details>
<summary>7. Як правильно оголошувати та використовувати функції в TypeScript із врахуванням типів?</summary>

#### TypeScript

- Функції визначаються так само, як у JavaScript, але в TypeScript можна явно
  задавати типи параметрів і результату:

```TypeScript
// З явними типами
function add(a: number, b: number): number {
  return a + b;
}

// Функціональний вираз
const greet = (name: string): string => {
  return `Hello, ${name}`;
};

// Необов’язковий параметр
function log(message: string, userId?: number): void {
  console.log(message, userId);
}
```

- Параметри можна робити обов’язковими, необов’язковими (?) або мати значення за
  замовчуванням.

- Тип повернення можна вивести автоматично, але для складних функцій краще
  вказувати явно.

- Для callback-ів та складних сигнатур використовують типи або інтерфейси
  функцій.

</details>

<details>
<summary>8. Що таке виведення типу (type inference) у TypeScript і як воно працює?</summary>

#### TypeScript

- Виведення типу — це механізм, коли TypeScript автоматично визначає тип змінної
  чи результату функції на основі наданого значення без явного оголошення.

#### Приклади:

```TypeScript
let count = 10;    // TS виводить: number
let message = "Hi"; // TS виводить: string

function add(a: number, b: number) {
  return a + b; // TS виводить: number (тип повернення)
}
```

- Перевага: менше коду, але збережена типобезпека.

- Ризик: у складних випадках краще явно вказувати тип, щоб уникнути
  неочікуваного any.

</details>

<details>
<summary>9. У чому різниця між let і const у TypeScript і як правильно їх використовувати?</summary>

#### TypeScript

`let` — дозволяє оголосити змінну, значення якої можна змінювати. Має блочну
область видимості.

`const` — створює змінну, якій можна призначити значення лише один раз. Також
має блочну область видимості.

#### Приклад:

```TypeScript
let counter: number = 1;
counter = 2; // ✅ можна

const name: string = "Alice";
name = "Bob"; // ❌ помилка
```

Рекомендація: за замовчуванням використовувати `const`, а `let` — лише коли
змінна дійсно змінюється.

Важливо: `const` не робить об’єкт immutable, змінювати внутрішні властивості все
одно можна:

```TypeScript
const user = { id: 1, name: "Alice" };
user.name = "Bob"; // ✅ дозволено
```

</details>

<details>
<summary>10. Яким чином можна скомпілювати TypeScript-файли у JavaScript?</summary>

#### TypeScript

- Використовується TypeScript Compiler (tsc).

- Основні варіанти:

```bash
# компіляція одного файлу

tsc file.ts

# компіляція проєкту з налаштуваннями tsconfig.json

tsc
```

- У tsconfig.json можна задати цільову версію JS (target), директорію виводу
  (outDir), модулі (module) тощо.

- Також можна включити watch mode:

```bash
tsc -w
```

У реальних проєктах часто використовують Babel, Webpack, Vite чи ts-node для
інтеграції компіляції у збірку чи запуск коду напряму.

</details>

<details>
<summary>11. Що таке класи в TypeScript і чим вони відрізняються від класів у звичайному JavaScript?</summary>

#### TypeScript

Класи в TypeScript — це надбудова над JS-класами. Вони працюють так само, як у
JS, але доповнені системою типів:

- можна оголошувати типи для полів, параметрів і повертаних значень;

- є модифікатори доступу (public, private, protected, readonly);

- є abstract класи та методи;

- підтримка implements для інтерфейсів;

- підтримка generics.

У рантаймі вони компілюються в звичайні JS-класи, а типи прибираються.

</details>

<details>
<summary>12. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>13. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>14. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>15. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>16. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>17. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>18. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>19. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>20. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>21. ???</summary>

#### TypeScript

- Coming soon...😎

</details>
