Download Link: https://assignmentchef.com/product/solved-dbs211-final-project
<br>
In this assignment, you create a simple HR application using the C++ programming language and Oracle server. This assignment helps students learn a basic understanding of application development using C++ programming and an Oracle database

<strong>Instruction:</strong>

In this assignment, we use the same database that you use for your labs.

<strong><em>Connecting to an Oracle database from a C++ Program</em></strong>

In your function <strong><em>main()</em></strong>, create a connection to your database.

You need to implement the following functions:

<strong><em>int menu(void);</em></strong>

The <strong><em>menu()</em></strong> function returns an integer value which is the selected option by the user from the menu. This function displays the following menu options:

<ul>

 <li>Find Employee</li>

 <li>Employees Report</li>

 <li>Add Employee</li>

 <li>Update Employee</li>

 <li>Remove Employee</li>

 <li>Exit</li>

</ul>

Before printing the menu, display the following title on the screen

Prompt the user to enter an option. If the user enters an incorrect option, the user is asked to enter an option again. When the user enters a correct option (1 to 5), the function returns the selected value.

If the user selects 6 (Exit), the program terminates.

<strong><em>int findEmployee(*conn,  int employeeNumber, struct Employee *emp);</em></strong>

This function receives a connection object, an integer number as the employee number, and a pointer to a variable of type Employee. The function returns 0 if the employee does not exist. It returns 1 if the employee exits.

To store the employee data from the <strong><em>findEmployee()</em></strong> function, we use a variable of type structure called Employee. The Employee structure has the following members:

<strong>struct Employee{</strong>

<strong>int employeeNumber;</strong>

<strong>char lastName[50]; </strong>

<strong>char firstName[50]; </strong>

<strong>char email[100];  </strong>

<strong>char phone[50]; </strong>

<strong>char extension[10]; </strong>

<strong>char reportsTo[100];  </strong>

<strong>char jobTitle[50]; </strong>

<strong>char city[50]; </strong>

<strong> </strong>

<strong>};</strong>

The <em>ReportsTo</em> member stores the first name and the last name of the employee who is the manager of the given employee number.

If the employee exists, store the employee data into the members of an Employee variable using the third parameter in the <strong><em>findEmployee()</em></strong> function which references to that variable of type Employee.<strong><u> </u></strong>

<strong><u>Note</u></strong>: For this report, you may need to query more than one table (join).

<strong><em>void displayEmployee(*conn, struct Employee emp);</em></strong>

If the user selects option 1, this function is called. First, prompt the user to enter a value for the employee number. Then, call function <strong><em>findEmployee()</em></strong> to check if the employee with the given employee number exists. If the returning value of function <strong><em>findEmployee()</em></strong> is 0, display a proper error message.

Sample error message:




Employee 1122 does not exist.




Otherwise, call the function <strong><em>displayEmployee() </em></strong>to display the employee information.

This function receives a connection pointer and values of a variable of type Employee and displays all members of the emp parameter.




Display the employee information as follows:




employeeNumber = 1002

lastName = Murphy

firstName = Diane

email = <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="60040d151210081920030c01131309030d0f04050c030112134e030f0d">[email protected]</a>

phone = +1 650 219 4782

extension = x5800

reportsTo =

jobTitle = President

city = San Francisco







<strong><em>void displayAllEmployees(*conn);</em></strong>

If the user selects option 2 (Employees Report), call function <strong><em>displayAllEmployees().</em></strong>

This function receives a connection pointer and displays all employees’ information if exists.

Write a query to select and display the following attributes for all employees.




E          Employee Name          Email                                       Phone              Ext       Manager————————————————————————————————————————

1002        Diane Murphy                          <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="ea8e879f989a8293aa89868b9999838987858e8f86898b9899c4898587">[email protected]</a>                 +1 650 219 4782       x5800

1056        Mary Patterson                         <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="066b766772726374756946656a6775756f656b6962636a656774752865696b">[email protected]</a>             +1 650 219 4782       x4611      Diane Murphy

1076        Jeff Firrelli                                <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="402a26293232252c2c2900232c21333329232d2f24252c232132336e232f2d">[email protected]</a>                   +1 650 219 4782       x9273      Diane Murphy

1143        Anthony Bow                            <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="dbbab9b4ac9bb8b7baa8a8b2b8b6b4bfbeb7b8baa9a8f5b8b4b6">[email protected]</a>                     +1 650 219 4782       x5428      Mary Patterson

1165        Leslie Jennings                          <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="96fafcf3f8f8fff8f1e5d6f5faf7e5e5fff5fbf9f2f3faf5f7e4e5b8f5f9fb">[email protected]</a>                 +1 650 219 4782       x3291      Anthony Bow

1166        Leslie Thompson                       <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="88e4fce0e7e5f8fbe7e6c8ebe4e9fbfbe1ebe5e7ecede4ebe9fafba6ebe7e5">[email protected]</a>             +1 650 219 4782       x4065      Anthony Bow

1188        Julie Firrelli                               <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="90faf6f9e2e2f5fcfcf9d0f3fcf1e3e3f9f3fdfff4f5fcf3f1e2e3bef3fffd">[email protected]</a>                   +1 215 837 0825       x2173      Anthony Bow

1216        Steve Patterson                        <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="ef9c9f8e9b9b8a9d9c8081af8c838e9c9c868c82808b8a838c8e9d9cc18c8082">[email protected]</a>             +1 215 837 0825       x4334      Anthony Bow

1286        Foon Yue Tseng                         <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a5c3d1d6c0cbc2e5c6c9c4d6d6ccc6c8cac1c0c9c6c4d7d68bc6cac8">[email protected]</a>                   +1 212 555 3000       x2248      Anthony Bow

1323        George Vanauf                          <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6a0d1c0b040b1f0c2a09060b1919030907050e0f06090b181944090507">[email protected]</a>                 +1 212 555 3000       x4102      Anthony Bow

1102        Gerard Bondur                         <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="a0c7c2cfcec4d5d2e0c3ccc1d3d3c9c3cdcfc4c5ccc3c1d2d38ec3cfcd">[email protected]</a>                 +33 14 723 4404       x5408      Mary Patterson

1337        Loui Bondur                              <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="59353b36373d2c2b193a35382a2a303a34363d3c353a382b2a773a3634">[email protected]</a>                 +33 14 723 4404       x6493      Gerard Bondur

1370        Gerard Hernandez                    <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="2e49464b5c404f404a4b6e4d424f5d5d474d43414a4b424d4f5c5d004d4143">[email protected]</a>             +33 14 723 4404       x2028      Gerard Bondur

1401        Pamela Castillo                         <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="aadac9cbd9dec3c6c6c5eac9c6cbd9d9c3c9c7c5cecfc6c9cbd8d984c9c5c7">[email protected]</a>                 +33 14 723 4404       x2759      Gerard Bondur

1702        Martin Gerard                          <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="bbd6dcdec9dac9dffbd8d7dac8c8d2d8d6d4dfded7d8dac9c895d8d4d6">[email protected]</a>                 +33 14 723 4404       x2312      Gerard Bondur

1621        Mami Nishi                               <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="d0bdbeb9a3b8b990b3bcb1a3a3b9b3bdbfb4b5bcb3b1a2a3feb3bfbd">[email protected]</a>                   +81 33 224 5000       x101        Mary Patterson

1625        Yoshimi Kato                            <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="96effdf7e2f9d6f5faf7e5e5fff5fbf9f2f3faf5f7e4e5b8f5f9fb">[email protected]</a>                    +81 33 224 5000       x102        Mami Nishi

1088        William Patterson                     <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="e592958491918097968a8ba586898496968c86888a81808986849796cb868a88">[email protected]</a>            +61 2 9264 2451       x4871      Mary Patterson

1611        Andy Fixter                               <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="305156594844554270535c51434359535d5f54555c535142431e535f5d">[email protected]</a>                   +61 2 9264 2451       x101        William Patterson

1612        Peter Marsh                             <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="f585989487869db596999486869c96989a91909996948786db969a98">[email protected]</a>                  +61 2 9264 2451       x102        William Patterson

1619        Tom King                                  <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="3a4e5153545d7a59565b4949535957555e5f56595b484914595557">[email protected]</a>                     +61 2 9264 2451       x103        William Patterson

1501        Larry Bott                                 <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="761a1419020236151a1705051f151b1912131a151704055815191b">[email protected]</a>                      +44 20 7877 2041     x2311      Gerard Bondur

1504        Barry Jones                               <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="3351595c5d564073505f5240405a505e5c57565f505241401d505c5e">[email protected]</a>                   +44 20 7877 2041     x102        Gerard Bondur




<strong><u>Note</u></strong>: For this report, you may need to query more than one table (join).

If the query does not return any rows, display a proper message:

There is no employees’ information to be displayed.

<strong><u>Note</u></strong>: For each query in your assignment, make sure you handle the errors and display the proper message including the error_code.

Error_code is a number returned if the query execution is not successful.