# HW07 grading policy

`NOTE: Any compile or runtime error (Segmentaion Fault) while running through any of the functions (IsInteger(), IsDouble(), IsValidIdentifier()) will cost you 15 points (you will get zero for that function). Plus, you will lose another 15 points because we have to use our own function in testAll.txt (sums up to 30 points). In case you submitted cases.txt, you will lose 1.67 points for the same reason (total of 31.67 points).`</br></br>



## IsInteger() function (15 points)
- In testInt.txt, you will find 15 different cases were used to verify your code. (1 point for each test case)
- In int_expected.txt, you will find the right output for each case in testInt.txt </br></br>
For testing, you can compile and run  your code through the following command:
<pre>
./pe07 testInt.txt -I > out.txt
</pre>
Then run the `diff` command to compare or you can use `vimdiff` command:
<pre>
diff -w -i -U 0 out.txt int_expected.txt
</pre>

	
## IsDouble() function (15 points):
- In testDbl.txt, you will find 15 different cases were used to verify your code. (1 point for each test case)
- In double_expected.txt, you will find the right output for each case in testDbl.txt </br></br>
For testing, you can compile and run  your code through the following command:
<pre>
./pe07 testDbl.txt -D > out2.txt
</pre>
Then run the `diff` command to compare or you can use `vimdiff` command:
<pre>
diff -w -i -U 0 out2.txt double_expected.txt
</pre>


## IsValidIdentifier() function (15 points):
- In testVID.txt, you will find 15 different cases were used to verify your code. (1 point for each test case)
- In validId_expected.txt, you will find the right output for each case in testVID.txt </br></br>
For testing, you can compile and run  your code through the following command:
<pre>
./pe07 testVID.txt -ID > out3.txt
</pre>
Then run the `diff` command to compare or you can use `vimdiff` command:
<pre>
diff -w -i -U 0 out3.txt validId_expected.txt
</pre>


## Test All (45 points)
- In testAll.txt, you will find 45 different cases were used to verify your code. (1 point for each test case)
- In all_expected.txt, you will find the right output for each case in testAll.txt </br></br>
For testing, you can compile and run  your code through the following command:
<pre>
./pe07 testAll.txt > out4.txt
</pre>
Then run the `diff` command to compare or you can use `vimdiff` command:
<pre>
diff -w -i -U 0 out4.txt all_expected.txt
</pre>

## Cases
`If you did not submit any cases you will lose 10 points`
- To test your cases.txt, we compile and run your code for your cases using the following command:
<pre>
./pe07 cases.txt > out5.txt //Your output
</pre>

Then we run our code and compare the two output files.




