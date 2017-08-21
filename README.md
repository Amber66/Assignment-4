# Assignment-4
Assignment 4 ( you can see the requirement in description of each program )
P.S :Exercise 13 has two ways to do( part a and b) 
//--------------------------------------------------------------------------
//Programmer:           Amber
//Date:                 14 August 2017
//Folder:               H:\C++ File
//Reference:            Assignment 4 exercise 1
//Description:          This program reads two strings and print as a string,
//                      the sum of the two numbers represented by the two 
//                      strings
//Guarantee:            Program works to full specifications

#include <iostream>
#include<conio>
#pragma hdrstop
using namespace std;

#include <tchar.h>

//---------------------------------------------------------------------------

#pragma argsused
int _tmain(int argc, _TCHAR* argv[])
{
	char num1[ 32 ];
	char num2[ 32 ];
	char sum[ 32 ];
	int sumOfNumbers;

	cout << "Enter the first number: ";
	cin >> num1;
	cout << "Enter the second number: ";
	cin >> num2;

	sumOfNumbers = atoi(num1) + atoi(num2);
	itoa (sumOfNumbers,sum,10);
	cout << sum;

	getch ();
	return 0;
}
//---------------------------------------------------------------------------

//############################################################################

//---------------------------------------------------------------------------
//Programmer:           Amber
//Date:                 14 August 2017
//Folder:               H:\C++ File
//Reference:            Assignment 4 exercise 12
//Description:          This program reads a namelist and prints the two names
//                      which occur first and last in alphabetical order
//Guarantee:            Program works to full specifications

#include <iostream>
#include<conio>
#pragma hdrstop
using namespace std;

#include <tchar.h>

//---------------------------------------------------------------------------

#pragma argsused
int _tmain(int argc, _TCHAR* argv[])
{
	char firstName[ 32 ];
	char lastName[ 32 ];
	char input[ 32 ];

	cout << " Enter the name or quit to exit: ";
	cin >> input;
	strcpy ( firstName, input );
	strcpy ( lastName, input );

	while ( strcmp( input, "quit" ) != 0 )
	{
		if ( strcmp( input, firstName ) < 0 )
			strcpy( firstName, input );
		else
			if ( strcmp( input, lastName ) > 0 )
				strcpy( lastName, input );

		cout << "enter the next name or quit to exit: ";
		cin >> input;
	}
	if ( strcmp( firstName, "quit" ) == 0)
		cout << "No name entered! ";
		else
			if ( strcmp( firstName, lastName ) == 0)
				cout << endl << "Please enter more names!" << endl;
			else
				cout << "Two or more names entered" << ensl;
				cout << "the firstname: " << firstName << endl;
				cout << "the lastnmae: " << lastName;

	getch ();
	return 0;
}
//----------------------------------------------------------------------------

//############################################################################

//----------------------------------------------------------------------------
//Programmer:           Amber
//Date:                 14 Aug 2017
//Folder:               H:\C++ File
//Reference:            Assignment 4 exercise 13 part(a)
//Description:          This program reads your names and print your initails 
//                      and your surname
//Guarantee:            Program works to full specifications

#include <iostream>
#include<conio>
#pragma hdrstop
using namespace std;

#include <tchar.h>

//---------------------------------------------------------------------------

#pragma argsused
int _tmain(int argc, _TCHAR* argv[])
{
	char myNames[ 64 ];
	int lastspace = 0;

	cout << " Enter your names : ";
	cin.get ( myNames, 64 );
	cout << "your name is: " << myNames[ 0 ] << ".";

	for ( int i = 0; i < strlen( myNames); i++ )
	{
		if ( myNames[ i ] == ' ' )
		{
			lastspace = i ;
		}
	}

	for ( int i = 0; i < lastspace; i++ )
	{
		if ( myNames[ i ] == ' ' )
		{
			i++;
			cout << myNames[ i ] << ".";
		}
	}

	for ( int i = lastspace + 1; i < strlen( myNames); i++ )
	{
		cout << myNames[ i ];
	}

	getch();
	return 0;
}
//---------------------------------------------------------------------------

//###########################################################################

//---------------------------------------------------------------------------
//Programmer:           Amber
//Date:                 14 Aug 2017
//Folder:               H:\C++ File
//Reference:            Assignment 4 exercise 13 part(b)
//Description:          This program reads your names and print your initails 
//                      and your surname as string
//Guarantee:            Program works to full specifications

#include <iostream>
#include<conio>
#pragma hdrstop
using namespace std;

#include <tchar.h>

//---------------------------------------------------------------------------

#pragma argsused
int _tmain(int argc, _TCHAR* argv[])
{
	char myNames[ 64 ] = " ";
	char initials[ 64 ] =" ";
	char temp[ 2 ];
	int lastspace = 0;

	cout << "Enter your names : ";
	cin.get ( myNames, 64 );

	for ( int i = 0; i < strlen( myNames); i++ )
	{
		if ( myNames[ i ] == ' ' )
		{
			lastspace = i ;
		}
	}

	initials[ 0 ] = myNames[ 0 ];
	strcat( initials, ". " );

	for ( int i = 0; i < lastspace; i++ )
	{
		if ( myNames[ i ] == ' ' )
		{	
			i++;
			temp[ 0 ] = myNames[ i ];
			strcat( initials, temp );
			strcat( initials, ". " );
		}
	}

	for ( int i = lastspace + 1; i < strlen( myNames ); i++ )
	{
		temp[ 0 ] = myNames[ i ];
		strcat( initials, temp );
	}
	cout << initials;

	getch();
	return 0;
	}
//---------------------------------------------------------------------------
Pseudocode
 
exercise 11

initialise num1 as string
initialise num2 as string
initialise sum as string
initialise sumOfNumbers as int

prompt and reade num1 and num2
pass num1 and num2 to atoi function
add num1 and num2 to sumOfNumbers
call itoa function  

print sum as string 

//---------------------------------------------------------------------------
exercise 12

initialise firstName 
initialise lastName 
initialise Input

prompt and read Input

firstName ← Input
lastName ← Input

Loop while sentinel not input

	if Input is before firstName
		firstName ←Input
	if Input is after lastName
		lastName ← userInput
	prompt and read Input again

End loop

if firstName = quit as string or lastName = quit as string
	print input names

else 
	if firstName = lastName
		print not enter the same names
	else
		if firstName != lastName
			print firstName and lastName
//---------------------------------------------------------------------------
exercise 13(a)

initialize myNames as string
initialize lastSpace as int

prompt and read myNames
print first character and ". "

Loop the length of myNames
	
	if current character = ' '
		lastSpace ← loop counter

End loop

Loop from 0 to lastSpace

	if current character = ' '
		loop counter increment
		print current character and ". "
End loop

Loop from lastSpace+1 to the length of myNames
	
	print current character

End loop
//----------------------------------------------------------------------------
exercise 13(b)

initialize myNames as string
initialize initials as string
initialize temp 
initialize lastspace as int

prompt and read myNames

Loop the length of myNames
	if current character = ' '
		lastSpace ← loop counter
End loop

Append ". " to initials

Loop from 0 to lastSpace
	if current character = ' '
		loop counter ++
		temp ← current character
		Append temp to initials 
		Append ". " to initials 
End loop

Loop from lastSpace+1 to the length of myNames
	initials ← current character
	Append ". " to initials 
End loop

print initials









