
**مقدمه**
<img src="attachments/Pasted%20image%2020250502141953.png" width="300px">

- در زبان پرتغالی LUA به معنای moon یا ماه می‌باشد . 
- 
- زبانی سبک ، high level و multi paradigm (الگو های برنامه نویسی متفاوت : Scripting, Procedural,Functional , Reflective , OOP) است که در سال ۱۹۹۳ توسط سه پژوهشگر برزیلی به نام‌های Roberto Ierusalimschy ، Luiz Henrique de Figueiredo و Waldemar Celes طراحی شد.
- به‌صورت کامل با زبان ANSI C پیاده‌سازی شده.
- از همان ابتدا به‌گونه‌ای طراحی شد که بتواند به راحتی به عنوان یک زبان extension مورد استفاده قرار گیرد، به این معنا که توسعه‌دهندگان بتوانند با استفاده از Lua، قابلیت‌های جدیدی را به برنامه‌های موجود اضافه کنند.
-  دلیل انتخاب این نام تاریخی جالب دارد: تیم توسعه در حال کار روی نسخه‌ی جدید زبانی قبلی به نام SOL (به پرتغالی «خورشید») بودند. یکی از همکاران در Tecgraf (Carlos Henrique Levy) پیشنهاد کرد زبان جدید را «Lua» (ماه) بنامند که در کنار نام SOL (خورشید) معنا دارد بدین ترتیب نام Lua انتخاب شد تا ارتباطی نمادین با زبان پیشین SOL برقرار باشد.

- از ابتدا بر چند اصل کلیدی بنا شد: سادگی، کوچکی، قابلیت حمل و قابلیت embed در برنامه‌های کاربردی
-  پیاده‌سازی آن بسیار سبک است و در سیستم‌عامل‌های مختلف اجرا می‌شود. یکی از ویژگی‌های بارز Lua استفاده از یک ساختار داده اساسی است: «جدول».
- این جدول‌ها در Lua آرایه‌های انجمنی (associative arrays) هستند که امکان استفاده از انواع مختلفی از مقادیر به‌عنوان کلیدها را فراهم می‌کنند. در واقع، جدول‌ها در Lua اجازه می‌دهند که مقادیر مختلفی از جمله مجموعه‌ها، ساختارهای پیوندی و دیگر ساختارهای داده به‌سادگی پیاده‌سازی شوند. از طرف دیگر، با استفاده از اعداد طبیعی به‌عنوان ایندکس‌ها می‌توانیم از جداول برای پیاده‌سازی آرایه‌ها استفاده کنیم. یکی از ویژگی‌های مهم Lua این است که این جداول، علی‌رغم اینکه آرایه‌هایی با ایندکس‌های عددی هستند، به‌طور داخلی به‌عنوان آرایه‌های واقعی پیاده‌سازی می‌شوند و از لحاظ استفاده از حافظه و عملکرد بهینه عمل می‌کنند .
-   شریک اصلی در توسعه نرم‌افزارهای Tecgraf در واقع Petrobras است ک هیکی از برگترین شرکت های نفی در بریزل می باشد. این شرکت نقش کلیدی در شکل‌گیری زبان برنامه‌نویسی Lua داشت، چرا که یکی از اصلی‌ترین اهداف تیم Tecgraf از توسعه زبان Lua، پاسخ به نیازهای Petrobras بود. 
- در واقع Petrobras به Tecgraf درخواست داده بود که درخواست‌های گرافیکی برای وارد کردن داده‌ها طراحی شوند که به کاربران این امکان را می‌دهد که به‌صورت تعاملی داده‌ها را وارد کنند. به این ترتیب، برنامه‌نویسان نیازی به ویرایش دستی ستون‌های اعداد نداشتند. بلکه تنها با کلیک کردن روی بخش‌های مربوط به یک نمودار، اطلاعات مورد نیاز برای شبیه‌سازی وارد می‌شد. همچنین از آنجا که ورودی‌ها به صورت خودکار تولید می‌شدند، این فرآیند هم ساده‌تر و هم مطمئن‌تر بود. پس به همین دلیل نیاز به یک زبان برنامه نویسی داشتند . 
- قبل تر دو زبان برنامه نویسی ساخته شده بود که DEL (Data-Entry Language) و SOL (Simple Object Language) بودند که درواقع زبان های Domain Specific بودند و lua درواقع نتیجه گسترش این دوزبان بر اساس نیاز های Petrobras بود.
-  در یک نگاه کلی، فلسفه طراحی Lua بر سادگی عمل و عدم پیچیدگی اضافی متمرکز بود. هیچ مفهوم عجیب و جدیدی در Lua معرفی نشد؛ توسعه‌دهندگان آن چیزهایی را که در زبان‌های دیگر دیده بودند برداشتند و مطابق سلیقه و نیاز خود بازآرایی کردند . در نتیجه Lua به زبانی تبدیل شد که به راحتی می‌توان آن را در برنامه‌های C جاسازی (Embed) کرد، برای کاربران غیرتخصصی قابل فهم است، و در عین حال ویژگی‌های قدرتمندی برای توسعه برنامه‌ها ارائه می‌دهد .
- 
![](attachments/Pasted%20image%2020250502132842.png)


![](attachments/Pasted%20image%2020250502141845.png)
Roberto Ierusalimschy



برای مثال
ما از طریق زبان اسکریپت های زبان lua و ارتباط گرفتن با api  wow میتونیم یه سری اسکریپت بنویسیم که مثلا ببینیم چندتا quest فعال داریم و نتیجه رو داخل chat بازی برای خودمون ببینیم :
```lua

local numQuests = C_QuestLog.GetNumQuestLogEntries()
print("You currently have " .. numQuests .. " quests active.")

```


**Table**
- در واقع تنها ساختمان داده موجود در زبان lua .
- در واقع و در اصل یک Associative array است که علاوه بر عدد به عنوان اندیس ، از string و یا هر مقدار دیگری نیز پشتیبانی می‌کند.
> a = {} -- create a table and assign its reference
> k = "x"
> a[k] = 10 -- new entry, with key="x" and value=10
> a[20] = "great" -- new entry, with key=20 and value="great"
> a["x"]
 --> 10
> k = 20
> a[k]
 --> "great"
> a["x"] = a["x"] + 1 -- increments entry "x"
> a["x"]
 --> 11
> a.x = 10 -- same as a["x"] = 10
> a.x -- same as a["x"]
--> 10 
> a.y  -- same as a["y"]
--> nil


- چطوریه که تیبل میتونه تمام این تایپ ها رو هندل کنه و دقیقا ساختارش چطوریه؟ 
-  بخش 1: جدول‌ها در Lua - تنها ساختمان داده

ساختار جدول در سورس کد Lua
داخل فایل `lobject.h`:
```c
struct Table {
  TValue *array;       /* بخش آرایه برای کلیدهای عددی */
  unsigned int alimit; /* اندازه آرایه */
  Node *node;          /* بخش هش برای کلیدهای غیرعددی */
  int lsizenode;      /* لگاریتم اندازه آرایه هش */
};

typedef struct Node {
  TValue key;         /* کلید */
  TValue val;         /* مقدار */
  int next;           /* برای زنجیره‌سازی برخورد */
} Node;
```

چرا برای کلید های عددی متوالی هم از hash استفاده نمیشود؟
1- کاربرد بالای کلید های عددی متوالی
2- هزینه زیاد Hash چه برای دسترسی چه برای ذخیره سازی

 ساختار `TValue` :
TValue هر نوع داده‌ای رو ذخیره می‌کنه:

```c
typedef struct TValue {
  union {
    lua_Number n;    /* عدد */
    int b;           /* بولین */
    GCObject *gc;    /* رشته، جدول، تابع و غیره */
  } value_;
	  int tt_;           /* نوع داده (مثل LUA_TNUMBER, LUA_TSTRING) */
} TValue;


```


***Hash***
هش فرآیندی است که یک داده ورودی (مثل رشته، عدد یا هر شیء دیگر) را به یک مقدار عددی ثابت، به نام هش‌کد، تبدیل می‌کند.

هش‌تیبل یک ساختار داده است که از تابع هش برای ذخیره و بازیابی داده‌ها استفاده می‌کند. در این ساختار:

- داده‌ها به‌صورت  key value ذخیره می‌شوند.
- کلید با تابع هش به یک index (هش‌کد) تبدیل می‌شود که مشخص می‌کند مقدار مرتبط با آن کلید کجا ذخیره شود(با استفاده از یک Hash Function)
- اگر برخورد (collision) رخ دهد (یعنی دو کلید به یک اندیس اشاره کنند)، هش‌تیبل از روش‌هایی مثل Chaining یا Open Addressing برای مدیریت این مشکل استفاده می‌کند. در داخل lua همانطور که مشخص است از روش Chaining برای حل برخورد استفاده می‌شود.

مدیریت Collison در lua :
```lua
/*
** Hash uses a mix of chained scatter table with Brent's variation.
** A main invariant of these tables is that, if an element is not
** in its main position (i.e. the 'original' position that its hash gives
** to it), then the colliding element is in its own main position.
*/

```

```lua
t = {}
t["apple"] = 1
t["banana"] = 2
t["cherry"] = 3
```

- "apple" → اندیس 1
- "banana" → اندیس 1 (برخورد با "apple")
- "cherry" → اندیس 2

_apple_
```text
node[0]: empty
node[1]: {key: "apple", value: 1, next: NULL}
node[2]: empty
node[3]: empty
```
( دلیل ایجاد چهار node ، ذخیره سازی لگاریتم بر پایه 2 اندازه هش است؛ در واقع اندازه هش همیشه مقداری به توان 2 می‌باشد که باعث ایجاد load factor (نسبت تعداد کلید ها به تعداد اندیس های ساخته شده ) مناسب می‎‌‎شود)

فرض میکنیم که کلید apple در اندیس 1 داخل hashtable ذخیره شود.
_banana_
حالا فرض میکنیم که banana هم در اندیس 1 داخل hashtable ذخیره شود؛ در این حالت در روش chaining عادی باید لیست پیوندی جداگانه ای درست شود ولی در lua به دلیل استفاده از Chained Scatter Table، داخل خود node ذخیره می‌شود و با next داخل نود دیگر(apple) در دسترس باشد. 
```text
node[0]: empty
node[1]: {key: "apple", value: 1, next: &node[2]}
node[2]: {key: "banana", value: 2, next: NULL}
node[3]: empty
```
_cherry_
فرض میکنیم cherry باید در اندیس 2 ذخیره شود. در این حالت بر اساس Brent’s Variation ما باید banana را به node دیگری منتقل کنیم و next نود اول را آپدیت کنیم تا cherry در واقع در جایگاه اصلی خود باشد (هدف  Brent’s Variation) - در حالتی که از این بهینه سازی استفاده نشود، cherry به node با اندیس 3 ام اضافه شده و با next node دوم به آن متصل می‌شود.
پس در نهایت :
```text
node[0]: empty
node[1]: {key: "apple", value: 1, next: &node[3]}
node[2]: {key: "cherry", value: 3, next: NULL}
node[3]: {key: "banana", value: 2, next: NULL}
```


مثال :

```lua
local t = {10, 20, ["name"] = "Lua"}
```

```c
Table *t = luaH_new(L); 

t->array[0].value_.n = 10; 
t->array[0].tt_ = LUA_TNUMBER; /* t[1] = 10 */ 

t->array[1].value_.n = 20; 
t->array[1].tt_ = LUA_TNUMBER; /* t[2] = 20 */ 

t->node[0].key.tt_ = LUA_TSTRING;
t->node[0].key.value_.gc = "name" ; 
t->node[0].val.tt_ = LUA_TSTRING;
t->node[0].val.value_.gc = "Lua" ;
```





**Love2D**

```lua

function love.load()

end

  

function love.update(dt)

end

  

function love.draw()

end
```

Love. run
```lua
function love.run()

    if love.load then love.load(love.parsedGameArguments, love.rawGameArguments) end

  

    -- We don't want the first frame's dt to include time taken by love.load.

    if love.timer then love.timer.step() end

  

    -- Main loop time.

    return function()

        -- Process events.

        if love.event then

            love.event.pump()

            for name, a,b,c,d,e,f,g,h in love.event.poll() do

                if name == "quit" then

                    if not love.quit or not love.quit() then

                        return a or 0, b

                    end

                end

                love.handlers[name](a,b,c,d,e,f,g,h)

            end

        end

  

        -- Update dt, as we'll be passing it to update

        local dt = love.timer and love.timer.step() or 0

  

        -- Call update and draw

        if love.update then love.update(dt) end -- will pass 0 if love.timer is disabled

  

        if love.graphics and love.graphics.isActive() then

            love.graphics.origin()

            love.graphics.clear(love.graphics.getBackgroundColor())

  

            if love.draw then love.draw() end

  

            love.graphics.present()

        end

  

        if love.timer then love.timer.sleep(0.001) end

    end

end
```


منابع :
- [سایت رسمی lua](https://www.lua.org/)
- [The Evolution of Lua ](https://www.lua.org/doc/hopl.pdf#:~:text=interface.%20Around%20mid,it%20has%20not%20changed%20since)
- [Source Code of Lua](https://github.com/lua/lua)
- [Programming in lua book](https://raw.githubusercontent.com/Alessana/ebooks/refs/heads/master/Programming%20in%20Lua%204th%20Edition.pdf)
- Grok And Chat GPT !
- [Steve's Teacher Youtube ](https://www.youtube.com/c/Stevesteacher)

