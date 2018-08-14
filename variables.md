# متغیرها

### متغیرها  {#variables}

در دنیای برنامه نویسی یکی از ابتدایی‌ترین و در عین حال مهم‌ترین مفاهیم متغیرها هستند. در واقع یک متغیر، یک مکان در حافظه است که دارای یک نام نمادین با عنوان شناسه می‌باشد و می‌تواند مقداری را در خود نگه‌داری کند. در واقع برای نگه‌داری و استفاده از بسیاری اطلاعات از متغیرها استفاده می‌کنیم. مقدار یک متغیر می‌تواند شامل هر نوع داده‌ای باشد.

#### انواع داده‌ها در جاوا {#data-types-in-java}

`Byte` : مخصوص نگه‌داری اعداد؛ 1 بایت

`short` : مخصوص نگه‌داری اعداد؛ 2 بایت

`int`: مخصوص نگه‌داری اعداد؛ 4 بایت 

`long` : مخصوص نگه‌داری اعداد؛ 8 بایت

`float` : مخصوص نگه‌داری اعداد اعشاری؛ 4 بایت

`double` : مخصوص نگه‌داری اعداد اعشاری؛ 8 بایت

`char` : مخصوص نگه‌داری یک کاراکتر؛ 2 بایت

`boolean` : مخصوص نگه‌داری مقادیر صحیح یا غلط؛ 1 بایت

#### چگونگی ساخت متغیرها در جاوا {#create-variable-in-java}

برای ساخت متغیرها در جاوا دو راه وجود دارد:

اولین راه مشخص نموندن نوع متغیر و سپس نام آن است. این روش بیشتر در صورتی استفاده می‌شود که قصد ندارید یک مقدار اولیه به متغیر اختصاص دهید. اما به هر حال این امکان نیز وجود دارد و می‌توانید در خط‌های بعدی با فراخواندن نام متغیر و یک علامت مساوی \(=\) در مقابل آن، مقداری از نوع متغیر به آن اختصاص دهید.

سینتکس کلی این روش به صورت زیر است:

```java
type variableName;
variableName = value;

// example:
int myInt;
myInt = 5;
```

راه دوم ساخت متغیر در جاوا، بدین صورت است که ابتدا نوع متغیر، سپس نام متغیر، و در نهایت با استفاده از علامت مساوی \(=\) مقدار اولیه ای به آن اختصاص می‌دهید:

```java
type VariableName = value;

// example:
double pi = 3.141592653589793;
```

**نکته:** به سادگی می‌توانید چندین متغیر از یک نوع را در یک خط تعریف کنید:

```java
int myInt, mySecondInt, myThirdInt;
double myDouble = 1.14, mySecondDouble = 2.14, myThirdDouble = 3.14;
```

#### رشته‌ها {#strings}

برای نگه‌داری یک متن یا رشته در داخل یک متغیر نیاز به نوع متغیر رشته‌ یا متن‌ دارید که جزء انواع متغیرهای اولیه نیستند اما در جاوا روش‌های مختلفی برای تعیین رشته‌ها وجود دارد:

۱. ساخت یک رشته با استفاده از یک سازنده:

```java
String myString = new String("this is my string!");
```

۲. تعریف متغیر رشته به صورت متغیرهای عادی:

```java
String myString = "this is my string!";
```

۳. ترکیب دو رشته و ساخت یک رشته:

```java
String myFirstString = "this is my first string";
String mySecondString = " and this is my second String";
String myThirdString = myFirstString + mySecondString
```

در این مثال متغیر `myThirdString` دارای مقادیر متغیر اول و متغیر دوم است و اگر آن را چاپ کنیم مقادیر این دو متغیر را برای ما نمایان می‌کند. در بخش عمل‌گرها به این موضوع به صورت جامع‌تر خواهیم پرداخت.

#### متغیرهای محلی {#local-variables}

به متغیرهایی که درون متدها، سازنده‌ها و یا بلوک‌ها ساخته می‌شوند متغیر محلی گفته می‌شود. این نوع از متغیرها زمانی که برنامه در هنگام اجرا وارد متد، سازنده و یا بلوک مورد نظر می‌شود ساخته و استفاده می‌شوند و پس از خروج از آن بلوک کد، نابود می‌شوند. همچنین این نوع از متغیرها فقط از داخل متد، سازنده و یا بلوکی که در آن ساخته شده قابل دسترسی هستند و خارج از آن‌ها قابل استفاده نیست.

به مثال زیر توجه کنید:



```java
public class LocalVar {
    void myMethod() {
        int myInt = 12;
    }
    public static void main(String[] args) {
        // main method
    }
}
```



در برنامه‌ی بالا متغیر `myInt` یک متغیر محلی برای متد `myMethod` است و فقط از داخل بلوک همان متد دردسترس است و در بلوک‌های دیگر نمی‌توان از آن استفاده کرد. برای مثال سعی می‌کنیم از متغیر `myInt`در متد اصلی برنامه‌ی خود استفاده کنیم و آن را چاپ کنیم:



```java
public class LocalVar {
    void myMethod() {
        int myInt = 12;
    }
    public static void main(String[] args) {
        System.out.println(myInt);
    }
}
```



حال اگر برنامه را کامپایل کنیم خطای زیر را خواهیم گرفت:

```text
➜  /tmp javac LocalVar.java 
LocalVar.java:6: error: cannot find symbol
        System.out.println(myInt);
                           ^
  symbol:   variable myInt
  location: class LocalVar
1 error
```

متن خطا بسیار صریح به ما می‌گوید که موفق به پیدا کردن متغیر مورد نظر ما در خط ششم، جهت چاپ نشده است و برنامه کامپایل نمی‌شود! دلیل نیز بسیار واضح است؛ همان‌طور که پیش‌تر نیز گفتیم، متغیرهای محلی هنگام ورود به بلوک کد خود ساخته شده و پس از خروج کامپایلر از بلوک مربوطه، آن متغیرها نیز از بین خواهند رفت. در نتیجه، خارج از بلوک کد`myMethod`متغیری به نام `myInt`وجود ندارد!

توجه کنید تغییردهنده‌های دسترسی را نمی‌توان برای متغیرهای محلی استفاده کرد. 

#### متغیرهای نمونه {#instance-variables}

متغیرهایی که درون کلاس‌ها هستند و خارج از هرگونه متد، سازنده و یا هر گونه بلوک کد دیگری هستند، متغیرهای نمونه نام دارند. متغیرهای نمونه هنگامی که یک شی با استفاده از کلمه‌ی کلیدی `new`ساخته می‌شود، ایجاد می‌شوند و زمانی که شی ساخته شده از بین برود، آن‌ها نیز به همراه آن از بین می‌روند.

 در واقع متغیرهای نمونه به نوعی متغیرهای محلی آن کلاس شناخته می‌شود و منطقی است که از درون تمام متدها، سازنده‌ها و یا بلوک‌های کدی که درون آن کلاس قرار دارند قابل دسترسی باشند.

متغیرهای نمونه به صورت پیش‌فرض دارای مقدار هستند و مقدار آن برای اعداد برابر با 0، برای boolean ها برابر با `false`و برای مرجع اشیا برابر با `null`است. متغیرهای نمونه به صورت مستقیم در داخل کلاس و با صدا زدن نام متغیر در دسترس هستند اما بدون روش static باید آن‌ها را با نام کامل به صورت `ObjectReference.VariableName` استفاده کرد.

نمونه‌ای از متغیرهای نمونه

```java
public class myNewClass {
    String name;
    public myNewClass(){
        System.out.println("the name is: " + name);
    }
}
```

در این تکه کد، متغیر `name` یک متغیر نمونه است. همچنین در تعریف متغیرهای نمونه می‌توانید از سطوح دسترسی نیز استفاده کنید، مثلا متغیری مانند زیر، فقط در کلاس خود قابل دسترسی است:

```java
private String name;
```



#### متغیر کلاس/استاتیک {#class-variables}

متغیرهای کلاس با نام استاتیک شناخته می‌شوند، چرا که هنگام ساخت آن‌ها باید از کلید واژه‌ی `static` استفاده کرد. همچنین آن‌ها در حافظه‌ی استاتیک ذخیره می‌شوند. این نوع از متغیرها خارج از هر نوع کلاس، متد، سازنده و یا هر بلوک کد دیگری قرار می‌گیرد و از تمام سایر کلاس‌ها نیز در دسترس خواهد بود. هنگامی که برنامه شروع به کار می‌کند، متغیرهای استاتیک ساخته می‌شوند و تا پایان کار برنامه از بین نمی‌روند.

معمولا متغیرهای کلاس به ندرت بدون این‌‌که متغیر ثابت \(Constant Variable\) باشند، استفاده می‌شوند. متغیرهای ثابت، متغیرهایی هستند که با کلید واژه‌‌هایی همچون `public`، `private`، `final` و `static` ساخته شده‌اند.

متغیرهای استاتیک شباهت نسبی‌ای به متغیرهای نمونه دارند؛ زیرا خارج از هرگونه بلوک کدی ساخته می‌شوند، اما به هر حال بیشتر متغیرهای استاتیک به صورت `public`ساخته می‌شوند. هر چند که این موضوع نیز بستگی به برنامه نویس و هدف استفاده از متغیر دارد.

متغیرهای استاتیک را می‌توانید بدون ساختن شی از روی کلاسِ متغیر، در هر کجا که می‌خواهید استفاده کنید. فقط کافیست نام کلاس و سپس نام متغیر را به صورت `ClassName.VariableName`صدا بزنید.

مقادیر پیش‌فرض متغیرهای استاتیک نیز مانند متغیرهای نمونه است. یعنی  مقدار آن برای اعداد برابر با 0، برای boolean ها برابر با `false`و برای مرجع اشیا برابر با `null`است.

هنگامی که یک متغیر استاتیک را به صورت همزمان `public static final`تعریف می‌کنید، نام متغیر باید تماما با حروف بزرگ باشد. در غیر این صورت نحوه‌ی نام گذاری متغیرها مانند متغیرهای محلی و نمونه است.

چند مثال از متغیرهای استاتیک با سطوح دسترسی و حالت‌های مختلف:

```java
public static name = "harry";
private static int age = 19;
public static final CONSTANTVARIABLE;
```



تا به اینجا استفاده‌های بسیاری از کلمات کلیدی‌ای همچون  `public` ، `private` و  ... کردیم. این‌ها جزئی از اصلاح کننده‌های دسترسی هستند که پیش‌تر معرفی شدند و در بخش بعد به صورت مفصل‌تر به آن‌ها خواهیم پرداخت.
