[Go back to Content](https://github.com/HuitingLiu/Blog/blob/master/content.md)

<a name="top"></a>
<h1 align="center">C:static variable and its scope</h1>

## 1.Static variable

<b/>Definition: In computer programming, a static variable is a variable that
has been allocated statically so that its lifetime or "extent" extends across
the entire run of the program.<b> ([Link](https://en.wikipedia.org/wiki/Static_variable))

## 2. Variables in C order by scope
* Global Variable  
Global Variable can be used by other modules after extern refrence

* Static Variable out of function  
Static Variable in file Level is only limited inside the module.

* Static Variable in function  
Static Variable in a function can only be used inside the function. When the function was called multiple time, the static variable only initialize only once.

```c  
void func() {
	static int a = 0;
	a++;
}

void main() {
	for (int i = 0; i < 10; i++)
		func();
}

The value of a will be: 0,1,2,3,4,5,6,7,8,9
```

* Local Variable   
Its lifetime is one function call.
