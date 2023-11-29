# Exception Handling :

<br>

## What is Exception? 

<br>

> * `BUG`
> * `Logical mistake of code which is unable to handle by compiler.`
> * Exception breakes the flow of compiler in between the process of execution.
> * It's a run time process(error).

<br><br>

<pre>
#include<iostream>
using namespace std;

int main() {
	
	int a,b,division;
	
	
	cout << "Enter a: ";
	cin  >> a;
	cout << "Enter b: ";
	cin  >> b;
	
	division = a/b; // Cannot divide by zero Exception
	
	cout << endl << endl << a << " / " << b << " : " << division << endl;
	
	cout << "Hello C++ Language" << endl;
	
}
</pre>

<br><br>

## Difference between Error & Exception :

<br>

Error | Exception
-------- | -----------
Syntax mistake of code which is unable to handle by compiler. | Logical mistake of code which is unable to handle by compiler.
It happens on compile time. | It happens on run time.
It Occures by Developer. | It Occures by Developer and User both.


<br><br>

## What is Exception Handling? 

<br>

> * `To verify the code in every possible way which can generate an exception and handle that all scenarious is called exception handling.`
> * It prevents the exceptions by some blocks by providing an optional code which will be only executed if exception is occured.
> * It can be handled by try and catch block.


<br>


### try block :

<br>

> * Write a code which may produce an exception.
> * Throw Value;

<br>

### catch() block :

<br>

> * Solution of that specific exception.

<br>

### Syntax :

<br>

<pre>
  try {
    //Statement which may cause an exception
		throw value/exception;
  }
  catch([excention/argument]) {
    //Solution for specific exception.
  }
</pre>

<br><br>

<pre>
#include<iostream>
using namespace std;

int main() {
	
	int a,b,ans;
	string error = "Can Not Divide By ZERO";
	
	
	cout << "Enter a: ";
	cin  >> a;
	cout << "Enter b: ";
	cin  >> b;
		
		
	try {
		if(b==0) {
			throw error;
		}
		else {
				ans = a/b;
				cout << "Ans: " << ans << endl;
		}
	}
	catch (string e) {
		cout << endl << e << endl; 
	}	
}
</pre>

<br><br>

## Implement general exception block (using spread(…) operator):

<br>

<pre>
	catch(...) {
		- general catch block
	}
</pre>

<br><br>

<pre>
#include<iostream>
using namespace std;

int main() {
	
	int a,b,ans;
	double x;
	string error = "Can Not Divide By ZERO";
	
	
	cout << "Enter a: ";
	cin  >> a;
	cout << "Enter b: ";
	cin  >> b;
		
		
	try {
		if(b==0) {
			throw error;
		}
		else {
				ans = a/b;
				throw x;
		}
	}
	catch (string e) {
		cout << endl << e << endl; 
	}	
	catch (int val) {
		cout << endl << "ANS: " << val << endl;
	}
	catch(...) {
		cout << endl << "General Exception" << endl;
	}
}
</pre>

<br><br>

## OOP :

<pre>
#include<iostream>
using namespace std;

class Div {
	
	int a,b;
	string error = "Can Not Divied By ZERO";
	
	public:
		
		void Divied() {
			cout << "Enter a: ";
			cin  >> a;
			cout << "Enter b: ";
			cin  >> b;
			
			if(b==0)
			{
				throw error;
			}else {
				
				throw a/b;
			}
		}
	
};


int main() {
	
	Div d1;
	
	try{
		d1.Divied();
	}
	catch(string e) {
		cout << endl << e << endl;
	}
	catch(int val) {
		cout << endl << "ANS : " << val << endl;
	}
	
}
</pre>










