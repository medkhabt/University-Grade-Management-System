# University-Grade-Management-System

> After attending the course LP002, Kennard completed a challengeable coursework, 
> with helping his instructor Henry Hong-Ning Dai to design a software for grade management.

------

### Software Demo

![UGMS](https://kennardwang.github.io/ImageSource/University-Grade-Management-System/UGMS.png)

------

### Development Environment

| Description | Specification |
|:---:|:---:|
| System | Windows 10 |
| Language | Java |
| JDK | 8u202 |
| IDE | Eclipse 2018-12 (4.10.0) |

------

### User Manual
+ Installation
  > 1. [Download](https://github.com/KennardWang/University-Grade-Management-System/releases) **jdk 8u202** and install.
  > 2. [Download](https://github.com/KennardWang/University-Grade-Management-System/releases) **UGMS_v2.1.jar**.
  > 3. Does not need other external plugins. You can execute jar file by `java -jar UGMS_v2.1.jar`.

+ Sort
  > 1. Click the **File** and choose **Open File** option.
  > 2. Choose a ***.txt*** course file and select the sort approach.
  > 3. Click the **Display** button.
  >
  > **P.S.** Before using GPA sort, please import required files first !

+ Query
  > 1. Click the **File** and choose **Import File** option.
  > 2. Import all the ***.txt*** course files which you need and then select the query approach.
  > 3. Remember to input the corresponding query message. 
  > Here is an example :
  >    + ID : **1X09853X-X011-XXXX**
  >    + Surname : **Weng**
  >    + WildCard(surname) : **W, We, We, Weng ...** ( The first letter must be upper case )
  >    + GPA Ranging: **> 3.0**, **= 3.0**, **< 3.0**, **>= 3,0**, **<= 3.0** ( Need space between the operator and the number )
  > 4. Click the **Query** button.

------

### Design

![general](https://kennardwang.github.io/ImageSource/University-Grade-Management-System/general.png)

+ Student Class

![student](https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Student.png)

+ Course Class

![course](https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Course.png)

+ SortAlgorithms Class

![sort](https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Sort.png)

+ GUI Class

![gui](https://kennardwang.github.io/ImageSource/University-Grade-Management-System/GUI.png)

------

### Data Structure
+ Student Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| sur/giv/id/score/Grade/GPA | Basic type (String/int/double) | The basic info of each student including surname, given name, id, score, Grade, GPA and so on |
| credit | 2-dimension array	| The student's real credit of every course. ( Parsed by Grade ) |
| takecourse | String array	| All the courses that the student takes |
| courseCredit | Int array | Corresponding credit of each taken course |
| Student()	| / |	Constructor |
| getsur(), getgiv(), getid(), getscore(), getGrade(), getStuData()	| / |	Methods to read data from the source file and return corresponding value |
| Grade2Credit() | /	| Parse Grade to credit |
| Credit2Grade() | / | Parse credit to Grade |
| computeGPA() | / | Using credit/takecourse/courseCredit to compute the total GPA |

+ Course Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| course/coName/credit/num | Basic type (String/int) |Basic info of a course|
| GraCount | Int array | Count the number of students of each Grade |
| highscore/lowscore/averscore | Int/double | Store the highest/lowest/average score of each course |
| Course() | / | Constructor |
| gerCourseData()	| /	| Read data from the source file and return corresponding value |

+ SortAlgorithms Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| exchange() | / | Exchange two elements in an array|
| less() | / |Compare two elements ( if former < latter then return true )|
| sort() |/|	Main sort algorithm |
| sortField()	| / |	Sort data in one aspect |
| sortWay() |	Stack |	Using stack to implement descent order |

+ GUI Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| contentPane	| JPanel |The JFrame window |
| fr |JFrame |The Frame|
| ReqInput | JTextField	| The input of query |
| CourseInput |	JTextField |	The input of course name |
| Screen |JTextArea	| The main screen |
| CourseList| JTextArea|	The list of course |
| RadioButton 1&2	| JRadioButton | The ascending & descending button |
| lblCredit	| JLabel |The credit label  |
| lblNumberOfStudents	| JLabel | The label of the student number |
| AddButton&DeleteButton | JButton | Add&Delete course |
| Choice_1 | JComboBox\<String> | Sort choice |
| MenuBar	| JMenuBar |	Menu bar |
| File |	JMenu |	Menu name |
| closeItem/openItem/importItem |	JMenuItem | Menu item |
| openDia	| FileDialog	| File dialog |
| sta	| Stack	| Store the course |
| stu	| Stack	| Store the Student element |
| index |	int	| Used to store course name |
| num	| int |	Index of choice 1 |
| num2 | int | Index of choice 2 |
| main() | / | Start of the whole program |
| myEvent()	| void | Operation of the file |
| GUI()	| / |	Constructor ( contains GUI components ) |
| IsDifferent() |	/	| Judge whether the new element is repetitive or not |
| IsDifferent(override)	| /	| Judge whether the new element is repetitive or not |
| readtxt()	| String array | Read the raw data and split it into groups |
| display()	| / |	Reveal the data |
| SortAndOutput()	| / | Execute sort and display method |
| Query()	| / |	Based on ReqInput, search for detailed data |

------

### Core Algorithm
+ Sorting
> Selection Sort, the complexity is O(N^2).

+ Searching
> Sequential Search, search by each inputted course individually, the complexity is O(N^2).

+ Analysis
> This program is based on once-input store, which means each time you input a course, the UGMS stores data of all the students who take this course at the same time. The number of one file data is less than 1000, so it is reasonable for a normal PC to execute for/while loop within 1 second ( Totally about 10^6, and 10^8 times per second for normal PC ).

------

### Feature
1. Implement user-friendly GUI.
2. Nice output format ( using JTable ).
3. Implement some advanced query functions ( such as Surname Wild Card, GPA ranging ). 
4. Allow the user to add and delete courses according to their requirement.
5. Can execute without other plugins and environment except JRE.
6. The UGMS would prompt you sometimes by showing a message window or a check box.
7. Unnecessary to worry about time consumption of sorting ( < 1 sec ).

------

### License  
+ [MIT License](https://github.com/KennardWang/University-Grade-Management-System/blob/master/LICENSE)

------

### Author
+ Kennard Wang ( 2019.11.5 )
