## Lab Report 5
Creating bash scripts to run commands greatly expedites the CLDQ process. The lab 4 tasks can be completed with 2 bash scripts:
One with the commands before editing `ListExamples.java` and one afterwards.

### Creating the Bash Scripts
The two scripts can be written locally containing commands used in lab 4, then either copied into the server using `scp`, or duplicated using `nano` inside the server. I chose the latter option using the following commands:
```
nano lab5cldq1.sh
nano lab5cldq2.sh
```

#### Bash Script 1:
<img width="960" alt="image" src="https://user-images.githubusercontent.com/116617731/224517681-7c92c818-9436-4d59-91db-564860dc4faf.png">

```
git clone git@github.com:Aotoda/lab7.git

cd lab7
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

nano ListExamples.java
```

#### Bash Script 2:
<img width="960" alt="image" src="https://user-images.githubusercontent.com/116617731/224517689-117789c4-b3e5-4e89-a824-11e4664d4766.png">

```
cd lab7

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

git add ListExamples.java
git commit -m "updated"
git push origin main
```

Note that Bash Script 2 must include the command `cd lab7` int he beginning unlike when inputting commands one-by-one as the machine's `pwd` does not stay as `lab7` after running BashScript 1.


### Running the Bash Scripts
Once the bash scripts are created, the lab 4 tasks can be completed very quickly.
Bash Script 1 can be run using the command:
```
bash lab5cldq1.sh
```
<img width="960" alt="image" src="https://user-images.githubusercontent.com/116617731/224517741-d9566cf6-dd19-4f97-ba0e-59f12c4324ce.png">

Which would prompt you to start editing the code.
<img width="960" alt="image" src="https://user-images.githubusercontent.com/116617731/224517725-b87dd576-86cc-450e-bbf2-441ebb420aec.png">

With the contents of line 40 copied onto the clipboard (where the error in the code is at line 42), the error can be found and fixed very quickly using the following comands I used to complete lab 4:
```
<Ctrl> + W
<Ctrl> + V
<Enter>
<down><down>
<right><right><right><right><right><right><right><right>

<Backspace>
2


<Ctrl> + O
<Enter>

<Ctrl> + X
```

Code in clipboard: `while(index2 < list2.size())`

Running Bash Script 2 requires no further input using the following command:
```
bash lab5cldq1.sh
```
<img width="960" alt="image" src="https://user-images.githubusercontent.com/116617731/224517755-88afa713-d8fa-4b48-b74c-ddde21675976.png">

Completing the lab 4 tasks.

### `fin.`
