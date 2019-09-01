// # Payroll_calc in C++
// Basic payroll calculator
// Dave Rowe

#include<iostream>
#include<iomanip>
#include<string>
using namespace std;

//main payroll program
int main()
{
	//variables
	string name;
	float hours;
	float othours;
	float wage;
	float taxes;
	float paycheck;
	const float taxrate = .08;			//employee tax rate

	//prompt user for name and payroll information
	cout << "Please enter your full name as displayed on your tax return: ";
	getline(cin, name);

	cout << "Please enter number of regular hours worked for this payroll period: ";
	cin >> hours;

	cout << "Please enter number of overtime hours worked for this payroll period: ";
	cin >> othours;

	cout << "Please enter your hourly wage: $ ";
	cin >> wage;

	//calculate employee paycheck
	paycheck = (hours * wage) + (othours * (wage * 1.5));
	taxes = paycheck * taxrate;
	paycheck = paycheck - taxes;

	//format and display paycheck
	cout << endl << fixed << setprecision(2);
	cout << name << " Your total amount earned this period is: $ " << paycheck + taxes << endl
		<< "Your taxes paid for this period is: $ " << taxes << endl
		<< "Your take home pay for this period is: $ " << paycheck << endl << endl;
	   	  
	system("pause");
	return 0;
}
