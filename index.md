# Lab 5

## Student Post
I'm trying to run the `grade.sh` script to grade a student's submission, but I'm encountering an error. The script successfully clones the repository and finds the `ListExamples.java` file. Anyway then it fails with the message

![Alt text](fifth-1st.png)
![Alt text](fifth-2nd.png)


## TA response 

It looks like there might be a syntax error in your `grade.sh` script on line 44. The `[[` command is used for conditional expressions in bash, but it seems like there might be a typo or incorrect usage. Could you share the code around line 44 of your `grade.sh` script? Additionally, try running the script with `bash -x grade.sh` to get more detailed output and see where it goes wrong.








