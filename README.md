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
<summary>12. Як правильно реалізувати спадкування класів у TypeScript?</summary>

#### TypeScript

Використовується ключове слово `extends`. Базовий клас може мати загальні
властивості/методи, похідний — успадковує їх і може перевизначати. При
перевизначенні конструктора обов’язково викликається `super()`.

```TypeScript
class Animal {
  constructor(public name: string) {}
  speak(): void {
    console.log(`${this.name} makes a sound.`);
  }
}

class Dog extends Animal {
  constructor(name: string, public breed: string) {
    super(name);
  }
  speak(): void {
    console.log(`${this.name} barks.`);
  }
}

const rex = new Dog("Rex", "Labrador");
rex.speak(); // Rex barks.
```

</details>

<details>
<summary>13. Які є модифікатори доступу в TypeScript і як вони впливають на властивості та методи класів?</summary>

#### TypeScript

TypeScript має 4 модифікатори доступу:

- `public` (за замовчуванням) – доступний скрізь.

- `private` – доступний тільки всередині цього класу.

- `protected` – доступний у класі та його нащадках.

- `readonly` – властивість доступна тільки для читання після ініціалізації.

Вони впливають лише на етапі компіляції (для контролю типів), у рантаймі
JavaScript цього обмеження немає.

</details>

<details>
<summary>14. Що таке абстрактні класи в TypeScript і для чого їх використовують?</summary>

#### TypeScript

Абстрактний клас — це клас, який не можна інстанціювати напряму. Він може
містити:

- реалізовані методи, які спільні для всіх нащадків,

- abstract методи без реалізації, які зобов’язані реалізувати похідні класи.

Призначення: задавати загальний контракт і базову поведінку для групи класів,
залишаючи конкретну реалізацію нащадкам.

```TypeScript
abstract class Shape {
  constructor(public color: string) {}
  abstract area(): number; // має реалізувати підклас
  describe(): void {
    console.log(`This shape is ${this.color}`);
  }
}

class Circle extends Shape {
  constructor(color: string, public radius: number) {
    super(color);
  }
  area(): number {
    return Math.PI * this.radius ** 2;
  }
}

const c = new Circle("red", 5);
c.describe(); // This shape is red
console.log(c.area()); // 78.5398...
```

</details>

<details>
<summary>15. Як працюють конструктори в класах TypeScript і які особливості їх використання?</summary>

#### TypeScript

Конструктор (constructor) — це метод для ініціалізації об’єкта класу.
Особливості у TypeScript:

- можна задавати типи параметрів;

- можна використовувати модифікатори доступу прямо в параметрах (`public`,
  `private`, `protected`, `readonly`) — тоді TypeScript автоматично створює
  відповідні поля;

- у похідних класах обов’язково викликається `super()` перед використанням
  `this`.

#### Приклад:

```TypeScript
class Person {
  constructor(public name: string, private age: number) {}
  greet() {
    console.log(`Hi, my name is ${this.name}`);
  }
}

class Employee extends Person {
  constructor(name: string, age: number, public position: string) {
    super(name, age);
  }
}

const emp = new Employee("Alice", 30, "Developer");
emp.greet(); // Hi, my name is Alice
console.log(emp.position); // Developer
```

</details>

<details>
<summary>16. Що таке декоратори в TypeScript для властивостей класу і як їх застосовувати?</summary>

#### TypeScript

Декоратори — це функції, які дозволяють змінювати або розширювати поведінку
класів, методів, властивостей або параметрів. Декоратор властивості отримує ціль
(target) та ім’я властивості (property key).

**Приклад використання властивості:**

```TypeScript
function logProperty(target: any, key: string) {
  let value = target[key];

  const getter = () => {
    console.log(`Getting ${key}: ${value}`);
    return value;
  };

  const setter = (newVal: any) => {
    console.log(`Setting ${key} to ${newVal}`);
    value = newVal;
  };

  Object.defineProperty(target, key, {
    get: getter,
    set: setter,
    enumerable: true,
    configurable: true
  });
}

class Person {
  @logProperty
  name: string = "";
}

const p = new Person();
p.name = "Alice"; // Setting name to Alice
console.log(p.name); // Getting name: Alice
```

Декоратори часто використовують для логування, валідації, DI (dependency
injection) та метаданих.

</details>

<details>
<summary>17. Як реалізуються та працюють геттери (get) і сеттери (set) у TypeScript?</summary>

#### TypeScript

Геттери та сеттери дозволяють контролювати доступ до властивостей класу.

- `get` — повертає значення властивості, дозволяє виконувати додаткову логіку
  при читанні.

- `set` — задає значення властивості, дозволяє перевіряти або модифікувати його
  перед присвоєнням.

#### Приклад:

```TypeScript
class Person {
  private _age: number = 0;

  get age(): number {
    return this._age;
  }

  set age(value: number) {
    if (value < 0) throw new Error("Age cannot be negative");
    this._age = value;
  }
}

const p = new Person();
p.age = 25;          // викликається set
console.log(p.age);  // викликається get -> 25
```

Геттери і сеттери працюють як звичайні властивості при доступі, але дозволяють
інкапсулювати логіку.

</details>

<details>
<summary>18. Як реалізується перевантаження методів у TypeScript?</summary>

#### TypeScript

TypeScript дозволяє перевантажувати методи через сигнатури, але тільки одна
реалізація. Це означає: можна оголосити кілька варіантів виклику методу з
різними параметрами, а в тілі методу реалізувати логіку з перевіркою
типів/кількості аргументів.

#### Приклад:

```TypeScript
class Calculator {
  add(a: number, b: number): number;
  add(a: string, b: string): string;
  add(a: any, b: any): any { // реальна реалізація
    return a + b;
  }
}

const calc = new Calculator();
console.log(calc.add(2, 3));       // 5
console.log(calc.add("Hello, ", "TS")); // Hello, TS
```

#### Особливості:

- Сигнатури визначають дозволені варіанти виклику.

- Реалізація повинна враховувати всі варіанти.

- У рантаймі перевантаження як у C#/Java не існує, це чисто типізаційний
  механізм.

</details>

<details>
<summary>19. Для чого використовується ключове слово static у класах TypeScript?</summary>

#### TypeScript

`static` дозволяє створювати члени класу (властивості або методи), які належать
самому класу, а не його екземплярам.

- До них звертаються через ім’я класу (ClassName.member), а не через об’єкт.

- Можна використовувати для констант, утилітарних методів та лічильників.

#### Приклад:

```TypeScript
class Counter {
  static count = 0;

  static increment() {
    Counter.count++;
  }
}

Counter.increment();
console.log(Counter.count); // 1

const c = new Counter();
// c.increment(); // ❌ помилка, increment — static
```

</details>

<details>
<summary>20. Як створити власний тип у TypeScript за допомогою псевдоніму (type alias)?</summary>

#### TypeScript

Псевдонім типу (`type`) дозволяє створити нове ім’я для будь-якого типу, включно
з об’єднаннями (`union`), перетинами (`intersection`) та функціями. Це зручно
для складних типів, повторного використання і документації коду.

```TypeScript
type ID = string | number;
type User = {
  id: ID;
  name: string;
  age?: number; // необов’язкове поле
};

type Callback = (result: string) => void;
```

Використовуємо як звичайний тип:

```TypeScript
const user: User = { id: 1, name: "Alice" };
```

Псевдоніми не створюють нових типів у рантаймі — це чисто типізація на етапі
компіляції.

</details>

<details>
<summary>21. Що таке union-типи в TypeScript і як їх застосовувати?</summary>

#### TypeScript

Union-тип (|) дозволяє змінній або параметру приймати декілька можливих типів.
Це зручно, коли значення може бути різного виду.

#### Приклад:

```TypeScript
type ID = string | number;

function printId(id: ID) {
  if (typeof id === "string") {
    console.log("ID (string): " + id.toUpperCase());
  } else {
    console.log("ID (number): " + (id * 10));
  }
}

printId("abc"); // ID (string): ABC
printId(123); // ID (number): 1230
```

#### Особливості:

- Потрібно робити type narrowing (перевірку типу) перед використанням
  специфічних методів.

- Можна комбінувати кілька типів, навіть `null | undefined`.

</details>

<details>
<summary>22. Що таке intersection-типи в TypeScript і як вони працюють?</summary>

#### TypeScript

Intersection-тип (&) поєднує кілька типів в один. Об’єкт повинен відповідати
всім об’єднаним типам одночасно. Це зручно для створення складних структур з
кількох контрактів.

#### Приклад:

```TypeScript
type Person = { name: string };
type Employee = { company: string };
type Developer = Person & Employee & { skills: string[] };

const dev: Developer = {
  name: "Alice",
  company: "TechCorp",
  skills: ["TypeScript", "React"]
};
```

#### Особливості:

- Якщо є конфліктні властивості з різними типами → результат може стати never.

- Добре поєднується з interface і type для композиції.

</details>

<details>
<summary>23. Що таке кортежі (Tuple types) у TypeScript і в яких випадках їх варто застосовувати?</summary>

#### TypeScript

Tuple — це масив із фіксованою кількістю елементів та визначеними типами для
кожної позиції. Використовуються, коли порядок і типи елементів наперед відомі.

#### Приклад:

```TypeScript
let user: [number, string, boolean];
user = [1, "Alice", true]; // ✅ правильний порядок і типи
user = ["Alice", 1, true]; // ❌ помилка
```

#### Особливості:

- Можна додати назви для кращої читабельності:

```TypeScript
type HttpResponse = [statusCode: number, message: string];
const res: HttpResponse = [200, "OK"];
```

- Підтримують optional та rest елементи:

```TypeScript
type RGB = [number, number, number?, number?]; // (R, G, B, A?)
```

Використовувати, коли треба передавати структуровані дані з фіксованим форматом
(наприклад, координати, записи логів, HTTP-відповідь).

</details>

<details>
<summary>24. Що таке твердження типів (type assertions) у TypeScript і для чого вони потрібні?</summary>

#### TypeScript

Type assertion — це спосіб сказати компілятору: «повір мені, я знаю реальний тип
цього значення». Це не змінює рантайм-поведінку, лише впливає на перевірку
типів.

#### Синтаксис:

```TypeScript
let value: unknown = "Hello TS";

// спосіб 1
let strLength: number = (value as string).length;

// спосіб 2 (JSX несумісний, тому рідше)
let strLength2: number = (<string>value).length;
```

#### Навіщо це корисно:

- коли TypeScript не може вивести точний тип;

- при роботі з any або unknown;

- при доступі до DOM-елементів:

```TypeScript
const input = document.getElementById("username") as HTMLInputElement;
console.log(input.value);
```

⚠️ Важливо: це не "перетворення типів", а підказка компілятору. Якщо ви
помилитеся, помилка проявиться вже у рантаймі.

</details>

<details>
<summary>25. Як працює перевірка типів за допомогою typeof у TypeScript і як її використовувати для type narrowing</summary>

#### TypeScript

`typeof` у TypeScript використовується для звуження union-типів під час
виконання. Це type guard, який дозволяє компілятору зрозуміти, який тип у
змінної в конкретній гілці коду.

#### Приклад:

```TypeScript
function printId(id: string | number) {
  if (typeof id === "string") {
    console.log("Uppercase ID:", id.toUpperCase()); // тут id: string
  } else {
    console.log("Numeric ID:", id.toFixed(2)); // тут id: number
  }
}
```

#### Особливості:

- `typeof` перевіряє типи рантайму: `string`, `number`, `boolean`, `object`,
  `function`, `undefined`, `symbol`, `bigint`.

- Використовується у функціях для безпечної роботи з union-типами.

Також typeof можна використовувати для отримання типу змінної чи функції при
оголошенні:

```TypeScript
let person = { name: "Alice", age: 30 };
type Person = typeof person; // { name: string; age: number }
```

</details>

<details>
<summary>26. Чи можна в TypeScript створювати типи на основі існуючих даних (значень) за допомогою виведення типів?</summary>

#### TypeScript

Так, можна. TypeScript дозволяє виводити типи з існуючих значень за допомогою
typeof і keyof.

#### Приклади:

1. **Отримання типу з об’єкта**

```TypeScript
const user = {
  id: 1,
  name: "Alice",
  isAdmin: true
};

type User = typeof user;
// User = { id: number; name: string; isAdmin: boolean }
```

2. **Отримання типів ключів**

```TypeScript
type UserKeys = keyof typeof user;
// "id" | "name" | "isAdmin"
```

3. **Комбінація з літеральними типами**

```TypeScript
const roles = ["admin", "user", "guest"] as const;
type Role = typeof roles[number];
// "admin" | "user" | "guest"
```

Це дозволяє уникати дублювання коду й гарантує синхронізацію типів з даними.

</details>

<details>
<summary>27. Що таке узагальнені типи (Generics) у TypeScript і для чого вони потрібні?</summary>

#### TypeScript

**Generics** — це параметризовані типи, які дозволяють писати універсальний і
багаторазовий код, зберігаючи типобезпеку. Вони дозволяють відкладати визначення
конкретного типу до моменту використання.

#### Приклад: функція без generics

```TypeScript
function identity(value: any): any {
  return value;
}
```

- Проблема: втрачається тип.

#### Приклад з generics

```TypeScript
function identity<T>(value: T): T {
  return value;
}

let num = identity<number>(42); // num: number
let str = identity("Hello"); // str: string (TS вивів тип автоматично)
```

#### Generics у класах і інтерфейсах

```TypeScript
class Box<T> { constructor(public content: T) {}
}

const stringBox = new Box("TS"); // Box<string>
const numberBox = new Box(123); // Box<number>
```

#### Навіщо:

- Писати гнучкий і типобезпечний код (колекції, утиліти, API).

- Уникати any і втрати інформації про тип.

- Дозволяє зв’язати вхідний і вихідний типи.

</details>

<details>
<summary>28. Як правильно створити узагальнену (generic) функцію в TypeScript?</summary>

#### TypeScript

Узагальнена функція визначається через параметр типу в кутових дужках `<T>`. Це
дозволяє зберегти типобезпеку і не втрачати інформацію про тип.

#### Базовий приклад

```TypeScript
function identity<T>(value: T): T {
  return value;
}

let n = identity<number>(10); // n: number
let s = identity("TS");       // s: string (тип виведено автоматично)
```

#### З кількома параметрами типів

```TypeScript
function pair<T, U>(first: T, second: U): [T, U] {
  return [first, second];
}

const result = pair("id", 123); // [string, number]
```

#### З обмеженням типу (extends)

```TypeScript
function getLength<T extends { length: number }>(item: T): number {
  return item.length;
}

getLength("Hello");       // 5
getLength([1, 2, 3]);     // 3
getLength(42);            // ❌ помилка, бо number не має length
```

Таким чином, generics роблять функції універсальними, але строго типізованими.

</details>

<details>
<summary>29. Як визначити узагальнені (generic) інтерфейси у TypeScript і для чого вони використовуються?</summary>

#### TypeScript

Узагальнені інтерфейси дозволяють описати контракт, який працює з різними
типами, зберігаючи типобезпеку. Для цього в інтерфейс додають параметри типів
`<T>` (або кілька).

#### Приклад: базовий generic-інтерфейс

```TypeScript
interface Box<T> {
  value: T;
}

const numBox: Box<number> = { value: 42 };
const strBox: Box<string> = { value: "Hello" };
```

#### З кількома параметрами

```TypeScript
interface Pair<K, V> {
  key: K;
  value: V;
}

const pair: Pair<string, number> = { key: "age", value: 30 };
```

#### Узагальнені інтерфейси з функціями

```TypeScript
interface Repository<T> {
  getAll(): T[];
  getById(id: number): T | null;
}

class UserRepo implements Repository<{ id: number; name: string }> {
  private users = [{ id: 1, name: "Alice" }];
  getAll() { return this.users; }
  getById(id: number) { return this.users.find(u => u.id === id) ?? null; }
}
```

#### Навіщо:

- дозволяють будувати універсальні API (репозиторії, сервіси, колекції);

- зберігають зв’язок між типами в методах/властивостях;

- уникання дублювання коду для різних сутностей.

</details>

<details>
<summary>30. Як працюють узагальнені (generic) типи у класах TypeScript і як їх застосовувати?</summary>

#### TypeScript

У TypeScript можна робити класи параметризованими типами, додаючи параметр `<T>`
після імені класу. Це дозволяє створювати універсальні класи, які працюють з
різними типами даних, зберігаючи типобезпеку.

#### Приклад базового generic-класу

```TypeScript
class Box<T> {
  constructor(public content: T) {}
  getContent(): T {
    return this.content;
  }
}

const numberBox = new Box<number>(123);
const stringBox = new Box<string>("Hello");

console.log(numberBox.getContent()); // 123
console.log(stringBox.getContent()); // Hello
```

#### Клас з кількома параметрами типів

```TypeScript
class Pair<K, V> {
  constructor(public key: K, public value: V) {}
}

const pair = new Pair<string, number>("id", 42);
```

#### Обмеження generic через extends

```TypeScript
class Collection<T extends { id: number }> {
  private items: T[] = [];
  add(item: T) { this.items.push(item); }
  getById(id: number): T | undefined {
    return this.items.find(i => i.id === id);
  }
}

const users = new Collection<{ id: number; name: string }>();
users.add({ id: 1, name: "Alice" });
```

#### Переваги:

- Універсальність класів без втрати типобезпеки.

- Повторне використання логіки для різних типів.

- Зв’язок між методами і властивостями через один параметр типу.

</details>

<details>
<summary>31. Як реалізувати узагальнене обмеження (generic constraint) у TypeScript і для чого воно потрібне?</summary>

#### TypeScript

У TypeScript можна обмежити generic-параметр за допомогою extends, щоб він
повинен був відповідати певному типу або інтерфейсу. Це дозволяє безпечно
використовувати властивості або методи об’єкта всередині функції або класу.

#### Приклад із функцією

```TypeScript
interface HasLength {
  length: number;
}

function logLength<T extends HasLength>(item: T): void {
  console.log(item.length);
}

logLength("Hello");      // ✅ рядок має length
logLength([1, 2, 3]);    // ✅ масив має length
logLength(42);           // ❌ помилка, number не має length
```

#### Приклад із класом

```TypeScript
class Collection<T extends { id: number }> {
  private items: T[] = [];
  add(item: T) { this.items.push(item); }
  getById(id: number): T | undefined {
    return this.items.find(i => i.id === id);
  }
}

const users = new Collection<{ id: number; name: string }>();
users.add({ id: 1, name: "Alice" }); // ✅ ok
```

#### Переваги:

- Дозволяє використовувати властивості або методи об’єкта без перевірок типу.

- Зберігає універсальність функцій і класів, але обмежує використання тільки
  сумісними типами.

</details>

<details>
<summary>32. Що таке дискримінований союз (Discriminated Union) у TypeScript і як він працює?</summary>

#### TypeScript

**Discriminated Union** — це патерн, коли `union` типів має спільну
властивість-дискримінатор (зазвичай літеральний тип), яка дозволяє компілятору
звузити тип під час перевірок.

#### Приклад:

```TypeScript
type Circle = {
  kind: "circle";
  radius: number;
};

type Rectangle = {
  kind: "rectangle";
  width: number;
  height: number;
};

type Shape = Circle | Rectangle;

function area(shape: Shape): number {
  switch (shape.kind) {
    case "circle":
      return Math.PI * shape.radius ** 2;
    case "rectangle":
      return shape.width * shape.height;
  }
}
```

#### Особливості:

- `kind` (або інша властивість) має літеральне значення, унікальне для кожного
  варіанту.

- Це дозволяє TypeScript робити type narrowing автоматично у `switch` чи `if`.

- Використовується для моделювання станів, подій, результатів API.

Фактично, це спосіб реалізації type-safe "enum-like" варіантів з різними
структурами даних.

</details>

<details>
<summary>33. Що таке утилітний тип Readonly у TypeScript і як його оголосити/використати?</summary>

#### TypeScript

`Readonly<T>` — це вбудований утилітний тип, який робить усі властивості об’єкта
тільки для читання (неможливо змінювати після ініціалізації).

#### Приклад використання:

```TypeScript
type User = {
  id: number;
  name: string;
};

const u: Readonly<User> = {
  id: 1,
  name: "Alice"
};

u.name = "Bob"; // ❌ Помилка: властивість доступна тільки для читання
```

#### Як оголошений всередині TS

```TypeScript
type Readonly<T> = {
  readonly [P in keyof T]: T[P];
};
```

- Тобто це mapped type, який додає модифікатор readonly до кожної властивості.

Використовується для іммутабельних даних, DTO та запобігання випадковим змінам.

</details>

<details>
<summary>34. Що таке mapped types у TypeScript і як їх використовувати?</summary>

#### TypeScript

**Mapped types** — це спосіб створювати нові типи на основі існуючих, проходячи
по ключах (`keyof`) та трансформуючи їх. Це використовується для створення
утилітних типів (`Readonly`, `Partial`, `Pick` тощо).

#### Базовий приклад:

```TypeScript
type User = {
  id: number;
  name: string;
  active: boolean;
  };

// Робимо всі властивості readonly
type ReadonlyUser = {
  readonly [K in keyof User]: User[K];
};
```

#### Використання з модифікаторами:

- `readonly` / `-readonly` → додає або прибирає "тільки для читання"

- `?` / `-?` → робить поле опціональним або обов’язковим

```TypeScript
type PartialUser = {
  [K in keyof User]?: User[K];
};
```

#### Generic-приклад:

```TypeScript
type MyMapped<T> = {
  [P in keyof T]: T[P];
};

type Test = MyMapped<{ a: string; b: number }>;
// { a: string; b: number }
```

#### Реальні приклади (вбудовані утиліти):

- `Readonly<T>` → робить усі властивості readonly

- `Partial<T>` → робить усі властивості опціональними

- `Required<T>` → робить усі властивості обов’язковими

- `Record<K, T>` → створює об’єкт, де всі ключі мають значення типу T

Mapped types корисні для масових перетворень типів без дублювання коду.

</details>

<details>
<summary>35. Що таке умовні типи (Conditional Types) у TypeScript і як вони працюють?</summary>

#### TypeScript

**Умовні типи** дозволяють описувати залежності між типами за допомогою
конструкції T extends U ? X : Y.

- Якщо T підтип U, результат буде X.

- Інакше — Y.

#### Базовий приклад:

```TypeScript
type IsString<T> = T extends string ? "yes" : "no";

type A = IsString<string>; // "yes"
type B = IsString<number>; // "no"
```

#### Використання з узагальненими типами:

```TypeScript
type ElementType<T> = T extends (infer U)[] ? U : T;

type A = ElementType<string[]>; // string
type B = ElementType<number>;   // number
```

#### Застосування у практиці:

```TypeScript
type ApiResponse<T> = T extends Error ? { success: false; error: T }
                                      : { success: true; data: T };

type R1 = ApiResponse<string>; // { success: true; data: string }
type R2 = ApiResponse<Error>;  // { success: false; error: Error }
```

#### Особливості:

- Працюють у поєднанні з generics, union та mapped types.

- Часто використовуються у вбудованих утилітах:

  - `Exclude<T, U>`

  - `Extract<T, U>`

  - `NonNullable<T>`

Умовні типи — це основа для гнучкої метапрограмінгової типізації.

</details>

<details>
<summary>36. Що таке індексні типи (Indexed Access Types) у TypeScript і як працює ключове слово keyof?</summary>

#### TypeScript

`keyof`

- keyof створює об’єднання (union) ключів заданого типу.

- Використовується для обмеження значень ключами інтерфейсу/типу.

```TypeScript
type User = { id: number; name: string; active: boolean };
type UserKeys = keyof User;
// "id" | "name" | "active"
```

#### Indexed Access Types (T[K])

- Дозволяють отримати тип значення за конкретним ключем.

```TypeScript
type UserIdType = User["id"]; // number
type UserNameOrActive = User["name" | "active"]; // string | boolean
```

#### Приклад разом

```TypeScript
function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}

const user: User = { id: 1, name: "Alice", active: true };

let nameValue = getValue(user, "name");   // string
let activeValue = getValue(user, "active"); // boolean
```

#### Навіщо це потрібно:

- Для generic-утиліт, які працюють із довільними об’єктами.

- Для побудови type-safe доступу до властивостей.

- Основа для утилітних типів (Pick, Omit, Record тощо).

</details>

<details>
<summary>37. У чому різниця між приведенням типів (type casting) і твердженням типів (type assertion) у TypeScript?</summary>

#### TypeScript

1. **Твердження типів (Type Assertion)**

- Це інструкція для компілятора, що значення має певний тип.

- Не змінює значення у рантаймі.

- Використовується, коли розробник краще знає тип, ніж TypeScript.

```TypeScript
let value: unknown = "Hello";
let strLength = (value as string).length; // "повір, це string"
```

2. **Приведення типів (Type Casting, runtime cast)**

- Це перетворення значення в інший тип у рантаймі (наприклад, Number("123") →
  123).

- Виконується реальною функцією чи оператором у JS.

```TypeScript
let str = "123";
let num = Number(str); // runtime casting → 123
```

#### Відмінність

- **Type assertion:** впливає тільки на компіляцію, ніяких змін у рантаймі.

- **Type casting:** реально змінює значення під час виконання.

У TypeScript під "casting" часто мають на увазі type assertions, але це не одне
й те саме.

</details>

<details>
<summary>38. Що таке утилітні типи Partial, Required, Readonly та Pick у TypeScript і для чого вони потрібні?</summary>

#### TypeScript

1. `Partial<T>`

- Робить усі властивості опціональними.

```TypeScript
type User = { id: number; name: string; };
type PartialUser = Partial<User>;
// { id?: number; name?: string }
```

- Використовується для об’єктів оновлення/патчів.

2. `Required<T>`

- Робить усі властивості обов’язковими (знімає ?).

```TypeScript
type UserOptional = { id?: number; name?: string; };
type RequiredUser = Required<UserOptional>;
// { id: number; name: string }
```

- Корисно для валидації, коли потрібен повний об’єкт.

3. `Readonly<T>`

- Робить усі властивості доступними тільки для читання.

```TypeScript
type User = { id: number; name: string; };
type ReadonlyUser = Readonly<User>;

const u: ReadonlyUser = { id: 1, name: "Alice" };
u.name = "Bob"; // ❌ Помилка
```

- Застосовується для іммутабельних даних.

4. `Pick<T, K>`

- Вибирає підмножину властивостей з типу T.

```TypeScript
type User = { id: number; name: string; active: boolean };
type UserPreview = Pick<User, "id" | "name">;
// { id: number; name: string }
```

- Корисно для DTO, селекторів, відображення лише потрібних полів.

Усі вони побудовані на mapped types + keyof.

Найчастіше застосовуються для гнучкої типізації API, DTO, form state, патчів
даних.

</details>

<details>
<summary>39. Що таке тип never у TypeScript і в яких випадках він застосовується?</summary>

#### TypeScript

`never`

- Це спеціальний тип, який означає значення, що ніколи не існує.

- Використовується там, де функція або вираз не повертає значення взагалі.

#### Основні випадки використання

1. **Функція, яка ніколи не завершується успішно**

```TypeScript
function fail(message: string): never {
  throw new Error(message);
}
```

2. **Функція з нескінченним циклом**

```TypeScript
function infiniteLoop(): never {
  while (true) {}
}
```

3. **Exhaustive checking (перевірка вичерпності union-типів)**

```TypeScript
type Shape = { kind: "circle"; radius: number }
           | { kind: "square"; side: number };

function area(shape: Shape): number {
  switch (shape.kind) {
    case "circle": return Math.PI * shape.radius ** 2;
    case "square": return shape.side ** 2;
    default:
      const _exhaustiveCheck: never = shape; // якщо додати новий варіант → помилка
      return _exhaustiveCheck;
  }
}
```

#### Ключові моменти

- `never` — підтип будь-якого типу, але жоден тип не є підтипом never (крім
  нього самого).

- Використовується для строгих перевірок типів і ситуацій, де значення бути не
  може.

never корисний у type-safe error handling та для гарантій повного покриття
union-типів.

</details>

<details>
<summary>40. Як організувати код за допомогою модулів у TypeScript?</summary>

#### TypeScript

**Основи модулів у TypeScript**

- Кожен файл з import або export стає модулем.

- Використовуються ключові слова export та import (як у ES6).

#### Приклад організації

`math.ts`

```TypeScript
export function add(a: number, b: number): number {
  return a + b;
}

export const PI = 3.14;
```

`app.ts`

```TypeScript
import { add, PI } from "./math";

console.log(add(2, 3)); // 5
console.log(PI);        // 3.14
```

#### Експорт за замовчуванням

```TypeScript
// logger.ts
export default function log(msg: string) {
  console.log("LOG:", msg);
}

// app.ts
import log from "./logger";
log("hello");
```

#### Перейменування та групування

```TypeScript
import * as MathUtils from "./math";
console.log(MathUtils.add(1, 2));
```

#### Організація проекту

- Файлова структура: групувати код за доменами (наприклад, services/, models/,
  utils/).

- Barrel files (індексні модулі): об’єднувати кілька експортувань в одному
  файлі.

```TypeScript
// utils/index.ts
export * from "./math";
export * from "./logger";

// app.ts
import { add, PI } from "./utils";
```

#### Конфігурація

- У `tsconfig.json` можна налаштувати:

  - "module": (esnext, commonjs, amd, залежно від оточення).

  - "baseUrl", "paths": для зручних alias-імпортів.

```json
{
  "compilerOptions": {
    "baseUrl": "./src",
    "paths": {
      "@utils/*": ["utils/*"]
    }
  }
}
```

Модулі в TypeScript = ті самі ES6 модулі, але з повною підтримкою типів.

</details>

<details>
<summary>41. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>42. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>43. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>44. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>45. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>46. ???</summary>

#### TypeScript

- Coming soon...😎

</details>
