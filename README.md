# tugas-progdas-nomer-2
#include <iostream>
#include <cmath>    // for sqrt() and pow()
using namespace std;

// Constant value for pi
const double PI = 3.1416;

// 🔹 FUNCTION SIGNATURES (function declarations)
double distance(double x1, double y1, double x2, double y2);
double radius(double x1, double y1, double x2, double y2);
double circumference(double r);
double area(double r);

// 🔹 MAIN FUNCTION
int main() {
    double xCenter, yCenter;  // coordinates of the circle's center
    double xPoint, yPoint;    // coordinates of a point on the circle

    cout << "Enter the coordinates of the circle's center (x1 y1): ";
    cin >> xCenter >> yCenter;

    cout << "Enter the coordinates of a point on the circle (x2 y2): ";
    cin >> xPoint >> yPoint;

    // 🔸 Actual parameters
    double r = radius(xCenter, yCenter, xPoint, yPoint);
    double d = 2 * r;
    double c = circumference(r);
    double a = area(r);

    cout << "\n=== CIRCLE CALCULATION RESULTS ===\n" << endl;
    cout << "Radius: " << r << endl;
    cout << "Diameter: " << d << endl;
    cout << "Circumference: " << c << endl;
    cout << "Area: " << a << endl;

    return 0;
}

// 🔹 FUNCTION DEFINITIONS

// a. Calculate the distance between two points
double distance(double x1, double y1, double x2, double y2) {
    // Formal parameters: x1, y1, x2, y2
    return sqrt(pow(x2 - x1, 2) + pow(y2 - y1, 2));
}

// b. Calculate the radius of the circle (using the distance function)
double radius(double x1, double y1, double x2, double y2) {
    // Formal parameters: x1, y1, x2, y2
    return distance(x1, y1, x2, y2);  // call the distance function
}

// c. Calculate the circumference of the circle
double circumference(double r)
{
    // Formal parameter: r
    return 2 * PI * r;
}

// d. Calculate the area of the circle
double area(double r)
{
    // Formal parameter: r
    return PI * pow(r, 2);
}
