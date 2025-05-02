
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




 **Scripting Language**
![](attachments/Pasted%20image%2020250427065148.png)


برای مثال
ما از طریق زبان اسکریپت های زبان lua و ارتباط گرفتن با api  wow میتونیم یه سری اسکریپت بنویسیم که مثلا ببینیم چندتا quest فعال داریم و نتیجه رو داخل chat بازی برای خودمون ببینیم :
```lua

local numQuests = C_QuestLog.GetNumQuestLogEntries()
print("You currently have " .. numQuests .. " quests active.")

```



**Difference Between Interpreted and Scripting Languages**

- منظور از Scripting هدف استفاده از زبان می‌باشد ولی منظور از Interpreted به روش اجرا اشاره می‌شود. ممکن است زبان های اسکریپتی امروزه نیز با Jit Compiler ها اجرا شوند . ( Just In Time Compile ) این روش بخشی از کد را در زمان اجرا به کد ماشین تبدیل می‌کند تا سرعت اجرا افزایش یابد. برای مثال، موتورهای جاوااسکریپت مثل V8 در مرورگر کروم از این روش استفاده می‌کنند 

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


***Table Traversal***
1- Pairs :We can traverse all key–value pairs in a table with the pairs iterator without any specific order :

```lua
t = {10, print, x = 12, k = "hi"}
for k, v in pairs(t) do
print(k, v)
end
```

>
--> 1 10
--> 2 function: 0x420610
--> k hi
--> x 12

ipairs : For lists, we can use the ipairs iterator:
```lua
t = {10, print, 12, "hi"}
for k, v in ipairs(t) do
print(k, v)
end
```

>
--> 1 10
--> 2 function: 0x420610
--> 3 12
--> 4 hi

In this case, Lua ensures the order.

```lua
t = {10, print, 12, "hi"}
for k = 1, #t do
print(k, t[k])
end
```
>
--> 1 10
--> 2 function: 0x420610
--> 3 12
--> 4 hi

The Problem With # ( Length Operator):

```lua
a = {}
a[1] = 1
a[10000] = 1
```

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

 ساختار `TValue` :
TValue هر نوع داده‌ای رو ذخیره می‌کنه (lobject.h):

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
چرا برای عدد ها هم از hash استفاده نمیشود ؟
1- کاربرد بالای کلید های عددی متوالی
2- هزینه زیاد Hash چه برای دسترسی چه برای ذخیره سازی

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

تعریف تابع‌های هش: توی ltable.c برای انواع کلیدها (مثل hashint, l_hashfloat, hashstr) تعریف شدن.
بررسی چگونگی مدیریت Collision :
```C
typedef union Node {
  struct NodeKey {
    TValuefields;  /* fields for value */
    lu_byte key_tt;  /* key type */
    int next;  /* for chaining */
    Value key_val;  /* key value */
  } u;
  TValue i_val;  /* direct access to node's value as a proper 'TValue' */
} Node;
```

```c
static void luaH_newkey (lua_State *L, Table *t, const TValue *key, TValue *value) {
  Node *mp;
  TValue aux;
  if (ttisnil(key)) luaG_runerror(L, "table index is nil");
  mp = mainpositionTV(t, key);  /* جایگاه اصلی کلید */
  if (!isempty(gval(mp)) || isdummy(t)) {  /* برخورد داریم؟ */
    Node *f = getfreepos(t);  /* جای خالی پیدا کن */
    if (f == NULL) {
      rehash(L, t, key);  /* جدول رو بزرگ کن */
      luaH_set(L, t, key, value);
      return;
    }
    Node *othern = mainpositionfromnode(t, mp);
    if (othern != mp) {  /* گره موجود توی جایگاه اصلیش نیست */
      while (othern + gnext(othern) != mp) othern += gnext(othern);
      gnext(othern) = cast_int(f - othern);
      *f = *mp;
      if (gnext(mp) != 0) gnext(f) += cast_int(mp - f);
      gnext(mp) = 0;
      setempty(gval(mp));
    } else {  /* گره توی جایگاه اصلیشه */
      if (gnext(mp) != 0) gnext(f) = cast_int((mp + gnext(mp)) - f);
      gnext(mp) = cast_int(f - mp);
      mp = f;
    }
  }
  setnodekey(L, mp, key);  /* کلید رو تنظیم کن */
  setobj2t(L, gval(mp), value);  /* مقدار رو تنظیم کن */
}
```
مراحل مدیریت برخورد :
محاسبه جایگاه اصلی:
با تابع هش (مثل hashstr یا hashint)، جایگاه اصلی کلید (mp) پیدا می‌شه.
چک کردن برخورد:
اگه جایگاه اصلی (mp) خالی نباشه (!isempty(gval(mp)))، یعنی برخورد داریم.
پیدا کردن جای خالی:
تابع getfreepos(t) یه نود خالی (f) توی جدول پیدا می‌کنه.
اگه جای خالی نباشه، rehash جدول رو بزرگ می‌کنه و دوباره تلاش می‌کنه.
رفع برخورد:
اگه گره موجود توی جایگاه اصلیش نباشه: Lua گره موجود رو به جای خالی (f) منتقل می‌کنه و کلید جدید رو توی جایگاه اصلی (mp) می‌ذاره.
اگه گره توی جایگاه اصلیش باشه: کلید جدید رو توی جای خالی (f) می‌ذاره و با فیلد next به زنجیره گره‌ها وصل می‌کنه.
تنظیم کلید و مقدار:
کلید و مقدار توی نود مناسب (چه mp چه f) ذخیره می‌شن.

**SET TABLE**
```lua
local l = {}
l[1] = 2
l["test"] = 3
```

>ByteCode 
2 [3] SETTABLE 0 -1 -2 ; 1 2
3 [4] SETTABLE 0 -3 -4 ; "test" 3

***Constant Table***


جدول ثابت‌ها (Proto.k) مقادیر ثابت (مثل عدد، رشته) رو ذخیره می‌کنه تا از تکرار و مصرف حافظه اضافی جلوگیری کنه.
```c
typedef struct Proto {
  TValue *k;  /* جدول ثابت‌ها */
  int sizek;  /* تعداد ثابت‌ها */
  /* سایر فیلدها */
} Proto;
```

```lua
local l = {}
l[1] = 2
l["test"] = 3
```
>Example Of Values in Constant Table
k[1] = 1 (عدد)
k[2] = 2 (عدد)
k[3] = "test" (رشته)
k[4] = 3 (عدد)

نکته : فقط برای ارتباط بین مفسر زبان و بایت کد Constant Table ها وجود دارند و مقادیر ذخیره شده در Table و یا دیگر مقادیر مقادیر اصلی از constant table واکشی شده و ذخیره می‌شوند. 

***SETTABLE***

```C
vmcase(OP_SETTABLE) {
  StkId ra = RA(i);  /* جدول (l) */
  const TValue *slot;
  TValue *rb = vRB(i);  /* کلید (1 یا "test") */
  TValue *rc = RKC(i);  /* مقدار (2 یا 3) */
  lua_Unsigned n;
  if (ttisinteger(rb)  /* کلید عدد صحیحه؟ */
      ? (cast_void(n = ivalue(rb)), luaV_fastgeti(L, s2v(ra), n, slot))
      : luaV_fastget(L, s2v(ra), rb, slot, luaH_get)) {
    luaV_finishfastset(L, s2v(ra), slot, rc);
  }
  else
    Protect(luaV_finishset(L, s2v(ra), rb, rc, slot));
  vmbreak;
}
```
Fast Path (مسیر سریع):
اگه:

جدول ساده باشه (نه متا‌تابع پیچیده داشته باشه)

کلید هم معمولی باشه (مثلاً عدد یا رشته)

اون وقت Lua می‌تونه خیلی سریع مقدار رو پیدا کنه یا بذاره، بدون اینکه بره سراغ متا‌تابع‌ها یا جست‌وجوی پیچیده.

تابع‌هایی مثل luaV_fastgeti یا luaV_fastget دقیقاً برای این مسیر سریع طراحی شدن.
 Slow Path (مسیر کند یا امن):
اگه:


جدول یه متامتابع داشته باشه (مثلاً _index یا _newindex)

نوع کلید یا جدول غیرمنتظره باشه

اون موقع باید بره مسیر کامل و کند (مثلاً luaH_get, luaV_finishset) تا همه چیز درست و طبق استاندارد بررسی بشه.




**Love2D**
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

