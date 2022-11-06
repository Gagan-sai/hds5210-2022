# Notes on the Midterm

* _Correctness    (out of 40):_ 39
* _Good Practices (out of 10):_ 9
* _Docs / Testing (out of 10):_ 10

_Details on the grading criteria for the midterm can be found on [Canvas](https://canvas.slu.edu/courses/28045/rubrics/23671)._

Overall, nicely done. I like that you included several test cases. Make sure that you try to include edge cases in your tests (i.e., including a condition where `None` is supposed to be returned).



## Step 1
* Just a note on convention - when you open a file and then read all the contents in using `json.load(f)`, you can move the rest of your code outside the `with` block.  At that point, Python is done reading from the file and you can let it close the file.


## Step 2
* I like the idea of using exception handling this way, but be careful. There are reasons your code might create an exception other than the billing code / service code combination not being present in the file. The requirements only say to return None if the combination can't be found. If there were other exceptions (like the section being there, but no `allowed_amount` value being present), those should not necessarily return None.  Your broad exception handling means those errors will simply pass by quietly. I've deducted one point from _Correctness_ for this.


## Step 3
* Great job. I like the use `'%A'` and having three conditions. It makes the code easier to read and trace back to the requirements.
* Your exception handling suffers the same problem as in step 2. Exception handling is great, but only catch the specific exceptions if you're going to use them this way.


## Step 4
* Nice use of `DictReader()` to make the code a bit more readable.
* You could have cleaned up the code a little bit by putting `if rate is not None: rate = 0` right after you get the adjusted rate.  Then you wouldn't have to repeat that code four times in your lower section. I've deducted 1 point from _Good Practices_ for this.