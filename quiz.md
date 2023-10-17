# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose
answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)
9b257


2. What is the SHA for the last commit associated with line 9 of this file?
b2ed3

3. What did line 12 of this file say in commit d1d83?
"I should really finish writing this."

4. What changed between commit e474c and 82045?
It looks like x["Gross"] was type casted to an int inside the lambda function and top_five got assigned to rows[:-6:-1] instead of rows[:-5:-1].

## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N
```
The merge happened with no problems and the contnents of top_N were placed into the test branch. There wasn't a merge conflict for me.

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```
There was a merge conflict when trying to get this to happen. However, the top_ten branch should have recieved the contents of test had there been no conflict. So no change happened to either branch in this case as we didn't resolve the conflict.

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```
Test got all the contents of top_ten and top_N. However to get there, we had to deal with a a merge conflcit when running the command "git rebase top_N". We resovled that issue by editing the top_N file and adding that version of process_movie_data.py to our git commit. Then we ran "git rebase --continue" to finish.


