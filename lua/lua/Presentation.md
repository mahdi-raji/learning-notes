**هدف از ساخت lua**
هدف از ساخت لوا، ارائه یک زبان اسکریپت‌نویسی قابل‌تعبیه ( embedded ) است که ساده، کارآمد، قابل‌حمل و سبک باشد. 

 **Scripting Language**
![](attachments/Pasted%20image%2020250427065148.png)**Programming languages** are a set of instructions that consist of words and symbols known as code or programs. Programming languages are also referred to as machine code or object code because it is compiled into machine-understandable code before getting executed. 

**A scripting language** is also a programming language but it does not need an extra step of compilation. Scripting languages are rather interpreted than complied, therefore it is also known as interpreter-based Language.

If you have a program running in a machine, and the code you're writing will be input to that program to be run then you are "scripting" that program.

برای مثال
ما از طریق زبان اسکریپت های زبان lua و ارتباط گرفتن با api  wow میتونیم یه سری اسکریپت بنویسیم که مثلا ببینیم چندتا quest فعال داریم و نتیجه رو داخل chat بازی برای خودمون ببینیم :
```lua

local numQuests = C_QuestLog.GetNumQuestLogEntries()
print("You currently have " .. numQuests .. " quests active.")

```



**Difference Between Interpreted and Scripting Languages**

- منظور از Scripting هدف استفاده از زبان می‌باشد ولی منظور از Interpreted به روش اجرا اشاره می‌شود. ممکن است زبان های اسکریپتی امروزه نیز با Jit Compiler ها اجرا شوند . ( Just In Time Compile ) این روش بخشی از کد را در زمان اجرا به کد ماشین تبدیل می‌کند تا سرعت اجرا افزایش یابد. برای مثال، موتورهای جاوااسکریپت مثل V8 در مرورگر کروم از این روش استفاده می‌کنند 
**Table**
![](attachments/Pasted%20image%2020250428072615.png)
- محاسبه‌ی آدرس رجیستر جدول: با RA(i) آدرس رجیستر مقصد (مثل R0) تعیین می‌شه.
- خواندن اندازه‌ی هَش: آرگومان B (log2 اندازه‌ی هَش + ۱) خوانده و به 2 به توان b-1  تبدیل می‌شه.
- خواندن اندازه‌ی آرایه: آرگومان C به‌عنوان اندازه‌ی اولیه‌ی آرایه خوانده می‌شه.
- تبدیل هَش سایز: اگه B > 0، اندازه‌ی واقعی هَش با شیفت بیت محاسبه می‌شه.
- تأیید آرگومان اضافی: با lua_assert سازگاری بیت k و آرگومان Ax چک می‌شه. در صورت وجود آرگومان اضافی، اندازه‌ی آرایه آپدیت و pc افزایش می‌یابد.