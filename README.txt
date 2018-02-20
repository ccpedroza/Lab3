/*
Christopher Pedroza
CPSC 121 Lab 3
02/15/18
*/

#include <iostream>
#include <string>


using namespace std;
//Function Declarations and definitions
void DrawRectangle(int width, int height) //If user selects rectangle and not a word this will be called
{
	for (int i = 0;i<height;i++) 
	{
		for (int j = 0;j<width;j++)
		{
			cout << "*";
		}
		cout << endl;
	}
}

void DrawRectangle(string word, int height) //if user selects word and rectangle this function will be called
{
	for (int i = 0;i<height;i++) 
	{
		cout << word; 
		cout << endl;
	}
}
void DrawTriangle(int size, bool pointingUp) //Function for triangle using size
{
	if (pointingUp == true)                      //boolean if statement used to print either up or down
	{
		for (int i = 0;i<size;i++) 
		{
			for (int j = 0;j <= i;j++) 
			{
				cout << "*"; 
			}
			cout << endl;
		}
	}
	else if (pointingUp == false)
	{
		for (int i = size;i > 0; i--) 
		{
			for (int j = i;j > 0; j--) 
			{
				cout << "*"; 
			}
			cout << endl; 
		}
	}
}
void DrawTriangle(string word, bool pointingUp)  //Function for triangle using words
{
	if (pointingUp == true)
	{
		for (int i = 0;i<word.length();i++)
		{
			for (int j = word.length() - i - 1; j <= word.length(); j++) 
			{
				cout << word[j]; 
			}
			cout << endl;
		}
	}
	else if (pointingUp == false)
	{
		for (int i = word.length();i > 0; i--) 
		{
			for (int j = word.length() - i; j < word.length(); j++) 
			{
				cout << word[j]; 

			}
			cout << endl;
		}
	}
}//loops until word is printed
int main()
{
	int n, rect, tri, Rwidth,
		Rheight, con, Twidth, point;
	string Rword, Tword;
	while (true)
	{
		cout << "Would you like to print a: " << endl
			<<"1.Rectangle"<<endl
			<<"2.Triangle";
		cin >> n;
		if (n == 1) 
		{
			cout << "Enter a choice" << endl
				<< "1.Word " << endl
			<<"2.Width";
			cin >> rect;
			if (rect == 1) 
			{
				cout << "Please enter word"<<endl;
				cin >> Rword;
				cout << "Please enter height" << endl;;
				cin >> Rheight;
				DrawRectangle(Rword, Rheight);
			}
			else if (rect == 2) 
			{
				cout << "Please enter width" << endl;
				cin >> Rwidth;
				cout << "Please enter height" << endl;
				cin >> Rheight;
				DrawRectangle(Rwidth, Rheight);
			}
			else {
				cout << "Invalid data" << endl;;
			}
		}
		else if (n == 2) 
		{
			cout << "Please enter your choice " << endl
				<< "1.Word " << endl
				<<"2.Width";
			cin >> tri;
			if (tri == 1)
			{
				cout << "Please enter word" << endl;
				cin >> Tword;
				cout << "Please enter direction" << endl
					<< "1.up" << endl
					<<"2.down";
				cin >> point;
				if (point == 1) // direction up
					DrawTriangle(Tword, true);
				else if (point == 2) // direction down
					DrawTriangle(Tword, false);
				else
					cout << "Invalid data" << endl;;
			}
			else if (tri == 2)
			{
				cout << "Please enter width"<<endl;
				cin >> Twidth;
				cout << "Please enter direction"<<endl
					<<"1.up"<<endl
					<<"2.down<<endl";
				cin >> point;
				if (point == 1) // direction up
					DrawTriangle(Twidth, true);
				else if (point == 2) // direction down
					DrawTriangle(Twidth, false);
				else
					cout << "Invalid data"<<endl;
			}
			else {
				cout << "Invalid data"<<endl;
			}
		}
		else {
			cout << "Invalid data"<<endl;
		}
		cout << "do you like to continue" << endl;
		cout << "1.Yes" << endl
			<< "2.No" << endl;
		cin >> con;//check if user would like to repeat
		if (con == 2)
			break;
	}


	return 0;
}
