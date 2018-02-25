# HW07 grading policy

`NOTE: Any compile or runtime error (Segmentaion Fault) while running through any of the functions (IsInteger(), IsDouble(), IsValidIdentifier()) will cost you 15 points (you will get zero for that function). Plus, you will lose another 15 points because we have to use our own function in testAll.txt (sums up to 30 points). In case you submitted cases.txt, you will lose 1.67 points for the same reason (total of 31.67 points).`</br></br>

How your grade is calculated>>

1. IsInteger() function (15 points):
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

	
2. IsDouble() function (15 points):
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


3. IsValidIdentifier() function (15 points):
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
	
