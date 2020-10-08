# POl----Rec-Cord.
//**************************************************************
//*** Title: Pol-to-Rec Conversion
//*** Course: CEPT 121-06 
//*** Developer: Brian Morgan
//*** Date: Sept28,20'
//*** Description: With the use of functions, create a program that's able to convery given coordinates to Rect to Pol, or Pol to Rect
//***              
//***
//**************************************************************
using namespace std;
#include <cmath> 
#include <iostream>
#include <iomanip>

   const double PI = 3.14159;
double RectangleToPolar(double x, double y) {
   
   double M = sqrt(pow(x,2) + pow(y,2)) ;
   
   return M;
  }
  
double PolarToRectangleX(double m, double a) {
   double x;
   
   a = a * (PI/180);
   
   x = m * cos(a)  ;
   return x; 
}

double PolarToRectangleY(double m, double a) {
   double y;
   
   a = a * (PI/180);

   y = m * sin(a)  ;
   
   return y;
   
}

int main() {
   char letter = 'a';
   
   double num1, num2;
 
 while (letter != 'Q' || letter != 'q') {
    
    cin >> letter >> num1 >> num2;
  
  if (letter == 'r' || letter == 'R' ) {
     cout << "REC -> POL +++++++++++++++" << endl; 
     cout << fixed << setprecision(2) << " REC:" << " X = "<< setw(8) << num1 << " Y = " << setw(8) << num2<< 
     " POL: M = " << setw(8) << RectangleToPolar(num1, num2) << " A = " << setw(8) << (atan2(num2,num1) * (180.0/PI)) << endl;
  }
  
  else if (letter == 'p' || letter == 'P') {
      cout << "POL -> REC +++++++++++++++" << endl;
      cout << fixed << setprecision(2) << " POL:" << " M = "<< setw(8) << num1 << " A = " << setw(8) << num2;
      cout << fixed << setprecision(2) << " REC:" << " X = "<< setw(8) << 
      PolarToRectangleX(num1,num2) << " Y = " << setw(8) << PolarToRectangleY(num1,num2);
      }
      
  else if (letter == 'q' || letter == 'Q') {
     break;
  }
  else {
     cout << "Format Error!" << endl;
  }
 
}
   return 0;
}
