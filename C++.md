C++  
***We are playing with data.*** 

*************  
# Table_of_Contents

1. [Useful](#useful)
2. [Compiler&Linker](#compiler_linker)
3. [how_it_works](#how_it_work)
4. [Variables](#variables)
5. [Functions](#functions)
6. [Header_files](#header_files)
7. [Conditions_and_branches ](#conditions_and_branches)
8. [Loops](#loops)
9. [Control_Flow](#control_flow)
10. [Pointers](#pointers)
11. [References](#references)
12. [Classes](#classes)
13. [Class vs Structures](#class_vs_structures)
14. [Const](#const )
15. [How_to_write_a_class](#how_to_write_a_class)
16. [Static_Cpp_Outside Class](#static_cpp_outside_class)
17. [Local_Static](#local_static)
18. [ENUMS](#enums)
19. [Constructor](#constructor)
20. [Destructor](#destructor)
21. [Inheritence](#inheritence)
22. [Virtual Fuctions](#virtual_fuctions)
23. [Interfaces_Pure_Virtual_Functions](#interfaces_pure_virtual_functions)
24. [Visibility](#visibility)
25. [Arrays](#arrays)
26. [Strings_in_cpp](#strings_in_cpp)
27. [String_Literals_in_Cpp](#string_literals_in_cpp)
28. [Mutable_keyword](#mutable_keyword)
29. [Constructor_Initializer_List](#constructor_initializer_list) 
*************
### Useful
  
* **#include **:library to use random number (can call rand())  
* **rand()%9** to call rand num between 1 and 9  
* **srand()**: truly rand with a seed as arg  
* **#include ** : to use time  
* **srand(time(0))**: seed the time to rand  
* **->**: it's to access a member function or a member variable or reference of an object through a pointer (with a regular variable or reference you would use . )  
  
   [TOC](#table_of_contents)
*************************  
  
### Compiler_Linker  
  
* Compiler changer code to be understandable by machine  
* Linker connect data  
  
You can trick compiler by just giving him what he wants:  
  
> For example if the compiler wants a function we can just create a new file with this function, then include in our main file this file then call the function before main like that:  
void Log(int p);  
  
   [TOC](#table_of_contents)
*****************  
  
### how_it_works
  
* Pre -processing :  
#include ... basically copy header files before your program  
**#include ** will make streaming fucntion like cout or cin available to use.  
  
> binaries, executable files  
> main function return int because return 0 if everything works  
  
   [TOC](#table_of_contents)
****************  
  
### Variables  
  
We can use Long and short variables.  
We can use unsigned variables.  
char can be number or caracter.  
**sizeof(bool)** : give size of variable  
  
> int -> 4 bit  
bool -> 1 bit  
double -> 8 bit  
  
   [TOC](#table_of_contents)
****************  
  
### Functions  
  
Function with return type:  
  
~~~cpp
type name (parameters)(){  
return type  
}  
~~~  
  
Function with no return type:  
(don't need return)  
~~~cpp
void name(parameters(){  
}  
~~~  
  
**parameters**: what has changed between blocs of code, between different uses of the function  
>Common task multiple time -> create a function  
  
We usually break up functions into Declaration and definition:  
**Declaration** -> header files  
**Definition** -> translation unit (.cpp files)  
  
   [TOC](#table_of_contents)
   
*******************  
  
### Header_files  
  
They are used to declare varibales or functions that are used in multiple programs. They are not used to make definition of the function but just to say that this function exist.  
  
**#include "name.h"** ("" include file are relative to the current file and <> have to be in one of the compiling include path directories )  
  
**name.h**  
  
Exemple:  
~~~cpp  
#pragma once // (declare only once,  
// to not include twice the same thing) (better)  
~~~  
or can :  
~~~cpp  
#ifndef _LOG_H  
#define _LOG_H  
#endif (same effect than pragma once)  
  
void initLog();  
void Log(const char* message);  
~~~  

 [TOC](#table_of_contents)
**********  
  
### Conditions_and_branches  
  
An if conditions is jumping to some part of memory  
  
> if statements would be avoid if you want a super fast code  
  
*Exemple* :  
~~~cpp 
int x = 5;  
bool comparisonResult = x ==5;  
if (comparisonResult){  
}  
~~~  
  
> if the if statement is only one line of code you can not use {}  
  
To check if **a number/or a pointer is a valid value**, we can use an if statement, **if null will not go into the loop**:  
~~~cpp  
if (x) { ==> equal to if (x! = null)  
"hello"}  
  
else if is equal to else{  
if {  
~~~  
   [TOC](#table_of_contents)
**************  
  
### Loops  
  
* **For**  
~~~cpp 
for (int i = 0; i<5; i++){  
}  
  
bool condition = true;  
for ( ; condition ; ){  
}  
  
for ( ; ; ){  
} endless loop  
~~~  
  
* **While**  
~~~cpp  
while ( i <5 ){  
}  
  
~~~  
  
* DO  
~~~cpp  
do{  
  
  
}while (i<5) : will be done at least one time  
~~~  
 [TOC](#table_of_contents)
  
************  
  
### Control_Flow  
  
**Gives more control how loops run**  
  
**continue* : inside loop, skip to the next iteration of this loop or end loop  
~~~cpp 
for (int i=5; i<5; i++){  
if (i %2 == 0)  
continue;  
}  
~~~  
**break** : inside loop or switch statement, get out of loop  
  
**return** : get out of the function  
  
   [TOC](#table_of_contents)
***************  
  
### Pointers  
  
**Managing Memory**  
A memory in a computer is a long straight street with a start and end, and house along with numbers (bits in computers)  
  
**pointer** : an integer that stores a memory address (address where the house is, where the specific bit of memory is)  
  
**void*** : we don't care what type the pointer is  
~~~cpp  
void* ptr = nullptr; // (memory address 0)  
int var = 8;  
void* ptr = &var; // store the memory address  
// of var in ptr  
~~~  
**Types doesn't matter for ptr**, it matters for manipulation of memories, but types matters for ptr when you want to read from ptr  
  
**Read from pointer** :  
~~~cpp  
int var = 8; //(stored on the stack)  
int* ptr = &var;  
*ptr = 10; // (access value of ptr, stored in a  
// memory address)  
~~~  
  
**Create a variable on the heat** :  
~~~cpp  
char* buffer = new char[8]; // (I want to allocate  
//some memory for me, asking for 8 bits of memory)  
memset( buffer, 0 , 8) // files 8 bit of memory  
//set to 0 (filles a block of memory with data)  
delete[] buffer; //( delete the memory used)  
~~~  
  
**Pointers are variables** :  
double pointer, ptr to ptr , variable storing memory adress pointing to an other variable stroing an another address that as the data  
  
**char** ptr** : a ptr to a ptr  
~~~cpp
int* m_X, *m_Y
~~~

   [TOC](#table_of_contents)
************  
  
### References  
  
**An extension of ptr**  
  
> pretty much the same things as ptrs  
  
**reference** : a way to reference an existing variable  
~~~cpp  
int a =5;  
int& ref = a;  
~~~  
> we created an allias, this variable doesn't realy exist for the computer, it's just the same variable all the time.  
  
**Comparison With ptr**:  
*With Ptr* :  
~~~cpp 
void Increment (int* value){  
(*value)++;  
}  
  
int main {  
int a =5;  
Increment(&a);  
}  
  
~~~  
*With reference* :  
~~~cpp 
void Increment (int& value){  
value++;  
}  
  
int main {  
int a =5;  
Increment(a);  
}  
~~~  
  
> Synthax sugar, cleaner, simpler  
  
>You have to immedialtly initialize.  
  
>Once you declared a reference, you can not change what it's refering too  
  
   [TOC](#table_of_contents)
********************  
  
### Classes  
  
**Object oriented programming**  
**Class** : put together data and fct  
~~~cpp  
Class player{ (unique type, creating a new variable type)  
public:  
int x, y  
int speed;  
};  
~~~  
**visibility** : how visible is the stuff inside the class (default private)  
**public** : can access to this variable outside this class  
**method** : function of a class  
~~~cpp  
Class player{  
public:  
int x, y  
int speed;  
void move (int xa, ya){  
x += xa *speed;  
y+=ya*speed;  
}  
~~~  
> Synthax sugar  
  
>They can't do anything than structures can't do.  
  
   [TOC](#table_of_contents)
********************  
  
### Class_vs_Structures  
  
**A class is private by default.**  
**A struct is public by default.**  
  
> Struct exist in part to have compatibility with C.  
~~~cpp  
struct player{  
}  
~~~  
**When do I use struct** : usage: playing on data, structure that represente variable, like a vector class;  
~~~cpp 
struct vec2{  
float x,y;  
void Add(const Vec2& other){  
	x = other.x +x;  
	y= other.y +y;  
	}
} 
~~~  
  
> Representing data in a structure, use struct.  
  
> I would never use inheritence with struct.  
  
   [TOC](#table_of_contents)
*******************  
  
### Const  
  
**const** : variables declared with ‘const’ added become constants and cannot be altered by the program  
  
* *Simple use* :  
 
const int Constant1=96;  
const int*  Constant2 : variable ptr to a cte int , cannot modify the content of the ptr
int const* Constant2: same ( look the position of the ptr symbol*)
int* const Constant3: cte ptr to a variable int  
int const * const Constant: cte cte  

* *Use of const in functions return* :  
  
The **const pointer to a variable** is useful for storage that can be changed in value but not in memory  
  
A **ptr to a const value** is useful for returning const strings and array from fcts which because they are implemented as ptrs, the prog will try to alter and crash. But you will know the error that the value was not suppose to be altered.  
  
* *In parameter passing* :  
  
void Subroutine4(big_structure_type const &Parameter1);  
which will cause the variable to be passed without copying but stop it from then being altered.  
  
* *Object oriented* :  
~~~cpp 
class Class2{  
void Method1() const;  
int MemberVariable1;  
};  
~~~  
which will ban Method1 in Class2 from being anything which can attempt to alter any member variables in the object.  

Example:
~~~cpp
#include <iostream>
#include <string>

class Entity{
private:
	int m_X, m_Y;
public:
	int GetX() const // this method is not going to modify the class, any members variables, read only
	{
		return m_X;
	}
	// 
	const int* const GetX() const { //return a cte ptr that has a cte content that can not modifed the class
		return m_X
		}
	void SetX(int x){ // not const, because we write to the class
		m_X = x;
		}
};
void PrintEntity(const Entity& e){
	std::cout<< e.GetX()<< std::endl; //if I have a const ref in the argument, I can only call a const method.
	}
~~~
  
   [TOC](#table_of_contents)
****************  
  
### How_to_write_a_class  
  
see code LogClass.cpp in home/Dev  
  
**To be completed**  
  
****************  
  
### Static_Cpp_Outside_Class  
  
* **Static outside a class**  
  
**static int s_Variable** : this variable is going to be linked only internly in this translation unit. It's kind of saying the variable private to the linker.  
  
> It's only going to be visible inside this .cpp file and not another.  
  
> We can't have two global variable with the same name.  
  
> We can use: extern int s_Variable  
  
**When do I use static outside a class** : if we don't need variable to be global, always being static unless we need cross linking between translation unit  
  
* **Static inside a class**  
  
> They are like a namespace but in a class.  
  
**When do I have to use static inside a class** : a data to be shared accross class, replace global variable. A data to be shared with all instances  
It's like a global variable but where we know exactly where is it.  
  
>Organization sugar.  
  
**Static methods** :  
  
> Have to use static arguments.  
  
A static method doesn't have a class instence.  
  
**When do I use static method** : Static data, data that doesnt change between class instence but we want actually to use inside our class  
  
   [TOC](#table_of_contents)
***********  
  
### Local_Static  
  
> Two parameters to look for variables: Live time of a variable / scope of the variable (where the variable can be use)  
  
**a static Local variable** : live time = the entire program / scop = limited inside this fct  
~~~cpp 
void Funtion(){  
	static int i = 0 ;  
	i++;  
	std::cout <<i<<std::endl;
	}
~~~
==  
~~~cpp
int i = 0 ;  
void Funtion(){  
	i++;  
	std::cout <<i<<std::endl;
	}
~~~
Example:  
~~~cpp
class Singleton{  
private:  
static Singleton* s_Instance;  
public:  
static Singleton& Get() { return *s_Instance;}  
void Hello(){}  
};  
Singleton* Singleton::s_Instance=nullPtr;  
int main(){  
Singleton::Get().Hello();  
}  
~~~  
==  
~~~cpp  
class Singleton{  
public:  
static Singleton& Get() {  
static Singleton instance;  
return *s_Instance;  
}  
void Hello(){}  
};  
  
int main(){  
Singleton::Get().Hello();  
}  
~~~

 [TOC](#table_of_contents)
***********  
  
### ENUMS  
  
**Enums** : a way to give a name to a value  
A way to name value  
> Helps to have a cleaner code  
  
Example :  
~~~cpp
enum Example : unisgned char { //int by default  
A = 0 ,B = 6 ,C = 8 //if not defined start from  
// 0 then increment 1 (A=0 , B=1,...)  
};  
int main {  
	Example value = B;  
	if (value ==1){  
	}
}
~~~

   [TOC](#table_of_contents)
*************  
  
### Constructor  
  
**Initialize a class**.  
  
A special type of method launched everytime we instanciated an object  
>Replace a void init()  
  
>A method that get called every time we construct an object  
  
~~~cpp 
Class Entity{  
public:  
	float X,Y  
	Entity() { // as to match the name of the class  
	}  
	Entity (float x, float y){  
		X=x;  
		Y=y;  
	} 
};
  
Entity e(10.0f,5.0.f);  
~~~  
  
>To delete the default constructor: Log() = delete;  

   [TOC](#table_of_contents)
****************  
  
### Destructor  
  
A special method gets called when an object get destroyed (for example when we get out of a fct loop)  
  
>Unitialize everything, opposite of the constructor, free memory  
  
~~~cpp  
~Entity() { // ~ to specify a destructor and not constructor  
}  
~~~  
  
   [TOC](#table_of_contents)
***************  
  
### Inheritence  
  
**inheritence** : allows base class contain basic functionnality then branch to have subclass from this parent class  
~~~cpp  
class Entity{  
public:  
	float X,Y;  
	void Move(float xa, float ya){  
		X=+ xa;  
		Y=+ya;  
		}  
};  
  
class Player : public Entity  
{  
public:  
	const char* name;  
};  
int main{  
	player.Move(5, 5);  
}  
~~~  
Player is a sub class of entity. It has the type player and entity.  
Playert has everything entity has.  
We can add informations that are not in entity in player.  
  
**Polymorphise**:  
We can also use Player everywhere we wanted to use Entity, because Player has everything from Entity + some specific stuff.  
Inheritence:  
  
> A way to extend an existing class, profide new functionnalities to a base class. Super class = Entity, base class  
  
   [TOC](#table_of_contents)
*************  
  
### Virtual_Fuctions  
  
**Virtual fuctions** : overwrite methods in subclass  
~~~cpp  
Class Entity{  
public:  
	std::string getName() { return "Entity";}  
};  
  
Class Player: public Entity{  
private:  
	std::string m_Name;  
public:  
	Player(const std::string& name)  
	: m_Name(name){}  
	std::string GetName() { return m_Name;}  
};  
void PrintName(Entity* entity){  
	std::cout >> entity->GetName() << std::endl;  
}  
int main()  
{  
	Entity* e = new Entity();  
	PrintName(e);  
	Player* p =new Player("Louis");  
	PrintName(p);  
	std::cin.get();  
}  
~~~  
Entity get print twice and not Louis .  
  
Because it go inside intity and call entity, it cause methods refer to the type.  
But we want the getName inside Player.  
Then we use virtual function, to overwrite the function in the base function and use the subclass function instead.  
~~~cpp 
Class Entity{  
public:  
	virtual std::string getName() { return "Entity";}  
};  
  
Class Player: public Entity{  
private:  
	std::string m_Name;  
public:  
	Player(const std::string& name)  
: m_Name(name){}  
	std::string GetName() override{ return m_Name;}  
};  
void PrintName(Entity* entity){  
	std::cout >> entity->GetName() << std::endl;  
}  
int main()  
{  
	Entity* e = new Entity();  
	PrintName(e);  
	Player* p =new Player("Louis");  
	PrintName(p);  
	std::cin.get();  
}  
~~~  
  
We add virtual in the base class in front of the fct name.  
We add override in then end of the name of the function that overwrite the fct in the base class. (c++11). (it's not a must but it helps for to make the code more clear and gives feedback on error in the name or else)  
  
**How does it work ?**  
Dynamic dispach using V-table, mapping for all the virtual function inside the base class to map them to the overwrite function.  
  
>Additional memory use when using virtual function.  
  
>Go trough the table to map the function.  
  
>The impact is still minimal.  
  
   [TOC](#table_of_contents)
   
*****************  
  
### Interfaces_Pure_Virtual_Functions
  
Allow us to define a function in a base class, that does not have an implementation and force subclass to implement that fct.  
  
We want to force the subclass to provide its own definition.  
  
It s commun to do a base class full of undefined methods and force the subclass to implement them, it's called an interface, a class that only consist on unimplemented methods, acting like a template.  
  
> It's not possible to instentiate that class. (Instentiate = Entity entity)  
  
~~~cpp  
virtual std:string getName() = 0; // =0 make a pure virtual fct that has to  
// be implemented in an another fct  
~~~  
~~~cpp  
Class Printable{  
public:  
	virtual std::string GetClassName() =0;  
};  
  
Class Entity : public Printable {  
public:  
	virtual std::string getName() { return "Entity";}  
	std::string GetClassName() {return "Entiry";}  
};  
  
Class Player: public Entity{  
private:  
	std::string m_Name;  
public:  
	Player(const std::string& name)  
: m_Name(name){}  
	std::string GetName() override { return m_Name;}  
	std::string GetClassName() {return "Player";}  
};  
void PrintName(Entity* entity){  
	std::cout >> entity->GetName() << std::endl;  
}  
  
void Print( Printable* obj){  
	std::cout << Entity->getName() << std::endl;  
}  
  
int main()  
{  
	Entity* e = new Entity();  
	Player* p =new Player("Louis");  
	Print(e);  
	Print(p);  
	std::cin.get();  
}  
  
~~~  
  
> There is no interface keyworld in C++, it's just a class.  
  
   [TOC](#table_of_contents)
*******************  
  
### Visibility

Object oriented programming.
**How visible members or methods are visible, who can see them, who can use them.**
>No effect on program performance, right better code.
Organization sugar.

Private, Protected, Public.
*Private* : 
~~~cpp
class Entity{
private: //only this Entity class can access this variable, read and write. 
	int X, Y;
};
~~~
friend can access private variable.
 
*Protected* :
~~~cpp
class Entity{
protected: //only this Entity class can access this variable, read and write. 
	int X, Y;
};
~~~
More visible than private, but less than public. This class and the subclass can access variables and methods, but not outside the class, for example inside the main. 

*Public* :
~~~cpp
class Entity{
public: //only this Entity class can access this variable, read and write. 
	int X, Y;
};
~~~
Everyone can access, class, subclass and outside.

Private tells you shouldn't be accessing this outside the class. It helps you understand a code.
We can ensure that people don't break things, called something than his not supposed to be called.

 [TOC](#table_of_contents)
***************

### Arrays

A collection of elements, a way to represent a collection of variables.

> Having multiple variables inside a single variable.

> Start with 0 in C++

~~~cpp
int main{
	int example[5];	
	example[0] =2;
	example[4] =4;
}
~~~
If you have an index problem (**memory access violation**), writing outside the bounds of the array, you will have memory address, you will access memory that don't belong to your array variable.
Always write in the bounds of your array, **hard to debug**, you have write in memory that you don't know may be in another variable memory.

> For loop is a good way to go through the entire array. 

Memory: you have 4 segments of 4 bits (int = 4 bit)  each in the example above, one after another in a row.

An array is an integer pointer to the block of memory that contains the 4 integers. 
~~~cpp
int main{
	int example[5];	
	int* ptr = example;
	example[2] =5;
	*(ptr + 2) = 5; // same meaning of the line above but takes more bits 
	*(int*)((char*)ptr + 8) = 5; //same meaning, with same bits
}
~~~
> When we are doing ptr arithmetic, in term of bits, the numbers of bits he is going to add depend on the type. For example, above we are going to add two times 4 bits because it's integer. 

*Array on the heat* 
~~~cpp
int main{
	int example[5]; //will be deleted at the end of main	
	int* another = new int[5]; //needs to be manualy deleted using delete keyword (delete[])
	for	(int i=0, i<5,, i++){
		example[i] = 2;
		anotger[i] = 2; 
		}
	delete[] another;
}	
~~~
Why dynamically allocate in the heat ?
Lifetime. 
But It takes a lot of performance.

~~~cpp
int count = sizeof(example) / sizeof(int); //to know the size of the array only on the stack
~~~
Not very beautiful and not very trust-able. 

*Other way* :
~~~cpp
class Entity{
public:
	static const int exampleSize = 5;
	int example[exampleSize]; //has to a compile time known const = static const
	Entity()
	{
		for (int i =0; i<exampleSize; i++)
			example[i] = 2;
	}
};
~~~
*In C++ 11* :
~~~cpp
class Entity{
public:
	std::array<int, 5> example; //type,size
	
	Entity()
	{
		for (int i =0; i<example.size(); i++)
			example[i] = 2;
	}
};
~~~

It's worth it to use c++11 array usually. It's safer because it maintained size. 
>They are called standard array and int array[5] are called raw array.

 [TOC](#table_of_contents)
 
***********

### Strings_in_cpp

An array of characters.
~~~cpp
int main{
	const char* name = "Louis"; //we can not change the content with const
	char name[5]= { 'L', 'o', 'u','i', 's',0} //equal to the line above
	}
~~~
ASCII representation in memory.
A string always ends with a 00 bit in memory. That's how the computer now, where the string end. 

*In C++*:
~~~cpp
#include <string>
int main{
	std::string name = "Louis";
	std::string name = std::string("Louis") + "Hello"; //adding strings
	bool contains = name.find("lo") != std::string::npos; //npos position
	name.size();
	}
~~~

You should use the std string library. 
***" string "*** : (double quote) means const char array.

~~~cpp

void PrintString(std::string string){
//Here we are copying string, thats very slow.
	std::cout << string << std::endl;
	}
void PrintString(const std::string& string){
//.Reference = won't be copied, const = means we promise not changing the string
	std::cout << string << std::endl;
	}
~~~
String copying is very slow, try to avoid.

 [TOC](#table_of_contents)
 
 ****************
### String_Literals_in_Cpp

***String Literals*** = "Louis" 
~~~cpp
	const char* name ="Louis"; // const remind you that you never modified a string defined 				like this
	const wchar_t* name2 = L"Louis"; //Wide characters
	const char16_t* name3 = u"Louis"; //UTF 16
	const char32_t* name4 = U"Louis"; //UTF 32
~~~
*string_literals library*:
~~~cpp
	using namespace std::string_literals; //c++14, you can put symbol in front or end of "" 
	std::wstring name0 = u8"Louis"s + U"Hello"; //the s at the end mean stand string
	const char* example = R"(Line1 //multi lines strings, R stands for roll
	Line2
	Line3
	Line4)";
~~~

 [TOC](#table_of_contents)
 
*****************
### Mutable_keyword 

*mutable with const*:
Can be change. 
~~~cpp
class Entity{
private:
	std::string m_Name;
	mutable int m_DebugCount = 0;
public:
	const std::string& GetName() const
	{
		m_DebugCount++;
		return m_Name;
	}
};
int main{
	Entity e;
	e.GetName();
	}
~~~

*mutable with lambda*:
a lambda is a throw away fct. 
~~~cpp
int main{
	Entity e;
	e.GetName();
	
	int x = 8;
	auto f = [=]() mutable //ref = & value = = 
	{	
		x++
		std::cout << x << std::endl;
	};
	f();
}
~~~

> it's very rare to use mutable in a lambda fct, it's not a common case. 

 [TOC](#table_of_contents)

**************

### Constructor_Initializer_List 
(Member initialiser list) 
It's a way to initialize our class members fct in the constructors.

~~~cpp
class Entity{
private:
	int m_score;
	std::string m_Name;
public:
	Entity() //default constructor
		: m_score(0), m_Name("Unknown") //member initializer list, in the same order that your declare the members
	{
		// constructor
		// m_Name ="Unknown"; //we can delete this now this we initialize above
		}
	Entity (const std::string& name)
		:m_Name(name)
		{	
		// m_Name = name;
		}
	const std::string& GetName() const
	{
		return m_Name;
	}
};
int main{
	Entity e;
	e.GetName();
	}
~~~
There is a difference of performance, using member initialiser list is more performante because when you don't  you create one initialization with the default constructor and one with the actual constructor.

Example: 

~~~cpp
class Example{
public:
	Example() 
		: m_Name("Unknown") 
		{	
		std::cout<< "Created Entity!" << std::endl;
		}
	Example(int x)
	{
		std::cout<< "Created Entity with " << x <<  std::endl;
		} 
	const std::string& GetName() const
		: m_Name(name)
	{
	}
};

~~~



>It's not only a matter of style, it actually make the code more performante !
Should use this all the time !!!!

 [TOC](#table_of_contents)
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTI2ODA4MTMxLDUyNDk1MzMzMiwtMTUwNT
kwMTg2NywtMTkyMjgwMjI3MywxMTkyNjkxODA0LC04Nzc0MzEx
MzMsLTE1MDA2MTg2NTUsMTI0MTQ5MDM2Myw3MjY0MjE2NjgsMT
AyNDA3NDQ0OSwtMjA2NDYwNjgwNiw1NDYxNDE1MCwtMjg5Mjcz
MTAwLC0xMDg4NzAwMTMxLC0xOTk1NzgwODc2LC0xNDU3OTE1NT
csMTEyNTQwODc1NywtOTY3NTA1MDk2LDYxMTUxMTM5OCwtMjkz
NjQ2MTZdfQ==
-->