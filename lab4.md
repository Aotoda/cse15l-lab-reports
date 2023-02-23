## Lab Report 4
### `<Ctrl> + R`
`<Ctrl> + R` is a very simple but useful shortcut to search through previous commandline inputs.
After completing the task the first time, I used `<Ctrl> + R` for every command-line input.
Even though some are called multiple times, every command is always used in the same _way_ in this lab,
so calling `<Ctrl> + R` on the command name always autocompletes and fetches the correct command.

#### Step 1 & 2: Setup
Delete the last fork you made in the repository settings, and fork the lab repository again.
<img width="557" alt="image" src="https://user-images.githubusercontent.com/116617731/220813822-dfd2ac6c-4b41-49a6-8c1e-ec2bd444c68b.png">
<img width="114" alt="image" src="https://user-images.githubusercontent.com/116617731/220813887-77a77812-8c49-4c55-b4ad-f1deb3cfccbd.png">

_Step 3_ is to start the timer.

#### Step 4: Log-in
Keys pressed:
```
<Ctrl> + R
ssh
<Enter>
```
Use `<Ctrl> + R` to access the previously issued ssh command:
```
ssh cs15lwi23abu@ieng6.ucsd.edu
```

#### Step 5: Clone the fork
Keys pressed:
```
<Ctrl> + R
clone
<Enter>
```
Use `<Ctrl> + R` to access the previously issued clone git command:
```
git clone git@github.com:Aotoda/lab7.git
```

#### Step 6: Run the tests
Keys pressed:
```
<Ctrl> + R
javac
<Enter>

<Ctrl> + R
java 
<Enter>
```
Use `<Ctrl> + R` to access the previously issued javac and java commands:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples 
```

#### Step 7: Edit the code
Keys pressed:
```
<Ctrl> + R
nano
<Enter>


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
Use `<Ctrl> + R` to access the previously issued nano command:
```
nano ListExamples.java
```

Use nano editor shortcuts to search for the unique contents of line 41, pasting from the clipboard.
Code in clipboard: `result.add(list2.get(index2));`
Arrow-key to the faulty code in line 43, column 12, and chang `index1` to `index2`.

Use more nano editor shortcuts to save the changes and exit the editor.

#### Step 8: Run the tests (again)
Keys pressed:
```
<Ctrl> + R
javac
<Enter>

<Ctrl> + R
java
<Enter>
```
Use `<Ctrl> + R` to access the previously issued javac and java commands:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples 
```

#### Step 9: Commit and push the changes
Keys pressed:
```
<Ctrl> + R
add
<Enter>

<Ctrl> + R
commit
<Enter>

<Ctrl> + R
push
<Enter>
```
Use `<Ctrl> + R` to access the previously issued `add`, `commit` and `push` git commands:
```
git add ListExamples.java
git commit -m "updated"
git push origin main
```

### `fin.`
