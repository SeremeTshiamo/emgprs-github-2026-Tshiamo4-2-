ConsoleSales
A Java console application that produces a sales report for game consoles (PS5, Xbox and Switch) across several South African cities. It totals the sales for each city and reports which city sold the most consoles overall.

Features
Prints a formatted table of console sales per city
Calculates the total sales for each city
Identifies the city with the highest total sales
Sample Output
=================================================
              CONSOLE SALES REPORT
=================================================
CITY             PS5     XBOX    SWITCH  TOTAL   
-------------------------------------------------
Cape Town        1000    2000    3000    6000    
Port Elizabeth   2000    3000    4000    9000    
Pretoria         1500    1100    1200    3800    
-------------------------------------------------
City With The Most Sales: Port Elizabeth
=================================================
Project Details
Item	Value
Group ID	com.mycompany
Artifact ID	consolesales-q1
Version	1.0-SNAPSHOT
Packaging	JAR
Java	17
Build tool	Apache Maven
IDE	Apache NetBeans
Main class	com.mycompany.consolesalesq1.ConsoleSalesReport
Project Structure
ConsoleSales/
├── pom.xml
└── src/
    └── main/
        └── java/
            └── com/mycompany/
                ├── consolesalesq1/
                │   ├── IConsoleSales.java        (interface)
                │   ├── ConsoleSales.java         (calculations)
                │   └── ConsoleSalesReport.java   (main class, prints the report)
                └── consolesalesq2/
                    ├── IConsoles.java            (interface)
                    └── Console.java              (console type, store, total sales)
Key Classes
ConsoleSales implements IConsoleSales and provides the report calculations:
TotalCitySales(int[] citySales) sums an array of console sales figures for one city.
TopCity(String[] cities, int[] totalSales) compares the totals and returns the name of the city that sold the most.
ConsoleSalesReport contains the main method. It holds the sales data, uses ConsoleSales to do the calculations and prints the report.
Console implements IConsoles and is an immutable class holding the console type, store name and total sales for one electronics store. It exposes getConsoleType(), getStore() and getTotalSales().
Requirements
JDK 17 or newer
Apache Maven 3.x (bundled with Apache NetBeans)
Apache NetBeans (optional, recommended)
How to Run
Option 1: NetBeans
Open NetBeans and choose File → Open Project, then select the ConsoleSales folder.
Right-click the project and choose Run, or press F6.
The report appears in the Output window.
Option 2: Command line
From the project folder:

cd C:\Users\emeris\Documents\NetBeansProjects\ConsoleSales
mvn compile
java -cp target/classes com.mycompany.consolesalesq1.ConsoleSalesReport
To run through Maven using the exec plugin (this is what NetBeans does):

mvn process-classes org.codehaus.mojo:exec-maven-plugin:3.5.1:exec -Dexec.executable=java "-Dexec.args=-classpath %classpath com.mycompany.consolesalesq1.ConsoleSalesReport"
Build Notes
Maven currently prints this warning when compiling:

location of system modules is not set in conjunction with -source 17
It is harmless, but you can remove it by using --release instead of -source/-target. In pom.xml, replace:

<maven.compiler.source>17</maven.compiler.source>
<maven.compiler.target>17</maven.compiler.target>
with:

<maven.compiler.release>17</maven.compiler.release>
Troubleshooting
Red squiggle under a package line: the package name must match the folder the file is in (for example ConsoleSales.java must be in com/mycompany/consolesalesq1/).
Cannot find IConsoleSales or IConsoles: make sure the interface is in the same package as the class implementing it, or add an import.
JAVA_HOME errors: point JAVA_HOME at a JDK 17+ installation, for example the JDK bundled with NetBeans.
Author
Emeris
