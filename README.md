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
<summary>20. ???</summary>

#### TypeScript

- Coming soon...😎

</details>

<details>
<summary>21. ???</summary>

#### TypeScript

- Coming soon...😎

</details>
