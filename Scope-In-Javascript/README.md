# Scope In Javascript
Javascript မှာ scope သုံးမျိုးရှီသည်။
* Block Scope
* Function Scope
* Global Scope

![javascript scope diagram](https://cdn.hashnode.com/res/hashnode/image/upload/v1600864549731/CPpg9u2gi.png)

## Block Scope
ES6 (2015) မတိုင်မီ၊ JavaScript တွင် Global Scope နှင့် Function Scope သာရှိသည်။

ES6 သည် အရေးကြီးသော JavaScript keywords အသစ်နှစ်ခုကို မိတ်ဆက်ခဲ့သည် let နှင့် const .

ဤ keywords နှစ်လုံးသည် JavaScript တွင် Block Scope ကိုပေးသည်။

{ } block တစ်ခုအတွင်းတွင် ဖော်ပြထားသော variables များကို block ပြင်ပမှ ခေါ်လို့မရပါ။

### Example
```javascript
    {
        let x = 2;
    }
    // x can not be used here
```
var keywords ဖြင့် ကြေညာထားသော variables များသည် block scope တွင် မရှိနိုင်ပါ။

{ } block တစ်ခုအတွင်းတွင် ကြေငြာထားသော variables များကို block ပြင်ပမှ ခေါ်နိုင်ပါသည်။
### Example
```javascript
    {
        var x = 2;
    }
    // x can be used here
```

## Local Scope
JavaScript function အတွင်း ကြေညာထားသော variables များသည် function အတွက် LOCAL ဖြစ်လာသည်။

Local variables များကို ၎င်းတို့၏ function များအတွင်းတွင်သာ အသိအမှတ်ပြုထားသောကြောင့်၊ အမည်တူ variables များကို မတူညီသော function များတွင် အသုံးပြုနိုင်ပါသည်။

function တစ်ခုစတင်သောအခါတွင် Local variable များကိုဖန်တီးပြီး function ပြီးသွားသောအခါတွင် ဖျက်လိုက်ပါသည်။
### Example
```javascript
    // code here can NOT use carName

    function myFunction() {
        let carName = "Volvo";
        // code here can use carName
    }

    // code here can not use carName
```

## Function Scope
JavaScript တွင် function scope ရှိသည်။ function တစ်ခုစီသည် scope အသစ်တစ်ခုကို ဖန်တီးသည်။

scope တစ်ခုအတွင်း သတ်မှတ်ထားသော variables များသည် function ပြင်ပမှ ခေါ်နိုင် မည်မဟုတ်ပါ။

var , let နှင့် const ဖြင့်ကြေငြာထားသော variables များသည် function တစ်ခုအတွင်းကြေငြာသောအခါ အတော်လေးဆင်တူပါသည်။

၎င်းတို့အားလုံးတွင် Function Scope ရှိသည်။
### Example
```javascript
    function myFunction() {
        var carName = "Volvo"; // Function Scope
    }
```

```javascript
    function myFunction() {
        let carName = "Volvo"; // Function Scope
    }
```

```javascript
    function myFunction() {
        let carName = "Volvo"; // Function Scope
    }
```

## Global JavaScript Variables
function တစ်ခုပြင်ပတွင် ကြေညာထားသော variables သည် GLOBAL ဖြစ်လာသည်။
### Example
```javascript
    let carName = "Volvo";
    // code here can use carName

    function myFunction() {
    // code here can also use carName
    }
```

## Global Scope
Globally ကြေငြာထားသော variables များ မည်သည့် function အပြင်တွင်မဆို Global Scope ရှိသည်။

Global variable များကို JavaScript ပရိုဂရမ်ရှိ မည်သည့်နေရာမှမဆို ခေါ်နိုင်ပါသည်။

var , let နှင့် const ဖြင့်ကြေငြာထားသော variable များသည် block တစ်ခုပြင်ပတွင်ကြေငြာသောအခါ အတော်လေးဆင်တူပါသည်။

၎င်းတို့အားလုံးတွင် Global Scope
ရှိသည်အတော်လေးဆင်တူပါသည်။
### Example
```javascript
    var x = 2; // Global Scope
```
```javascript
    let x = 2; // Global Scope
```
```javascript
    const x = 2; // Global Scope
```

## Automatically Global
မကြေငြာရသေးသော variable တစ်ခုသို့ value တစ်ခုသတ်မှတ်ပါက၊ ၎င်းသည် အလိုအလျောက် GLOBAL variable ဖြစ်လာမည်ဖြစ်သည်။
### Example
```javascript
    myFunction();

    // code here can use carName

    function myFunction() {
        carName = "Volvo";
    }
```

## Lexical Scope
Lexical scope သည် parent scope မှ variable များကို ဝင်ရောက်ရန် function scope တစ်ခုအတွက် စွမ်းရည်ဖြစ်သည်။ child function လုပ်ဆောင်ချက်ကို parent function ၏ lexically bound ဟုခေါ်သည်။

![lexical scope diagram](https://miro.medium.com/max/1400/0*vbTvsWC84WFrnrMI.png)

```javascript
    var a = 10; // variable a assigned to 10

    var func = function (){ // outermost function
        var b = 20;
        console.log("a and b is accessible (outer):", a, b);
        var innerFunc= function (){ // innermost function
            var c = 30;
            console.log("a and b and c is accessible (innner):", a, b, c);
        }
    innerFunc();
    return;
}
func(); // invoke function func 
console.log("only a is accessible (global):", a);
```
အထက်ဖော်ပြပါ ကုဒ်တွင်၊ variable a ၏ တန်ဖိုးသည် Global Scope တွင် ရှိနေသောကြောင့် function အားလုံးမှ ခေါ်နိုင်သည်။ variable b သည် func function တွင်သတ်မှတ်ပေးထားသောကြောင့် func function အပြင်ဘက်မှ ခေါ်ခွင့်မရှိပါ။ အဘယ်ကြောင့်ဆိုသော် variable သည် variable func တွင် သတ်မှတ်ထားသော function အတွက် local scope ဖြစ်သောကြောင့်ဖြစ်သည်။ နောက်ထပ်သတိပြုရမည့်အချက်မှာ innerFunc variable တွင်သတ်မှတ်ထားသော function သည် variable b နှင့် c ကိုခေါ်နိုင်သည်။