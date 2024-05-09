# Lab 3

## Part 1
### Test which ends up not a Failure and another that does repectively
```java
@Test
public void testReverseInPlaceNoFailure() {
    int[] original = new int[]{};
    ArrayExamples.reverseInPlace(original);
    assertArrayEquals(new int[]{}, original);
}
```

```java
@Test
    public void testReverseInPlaceFailure() {
        int[] original = new int[]{1, 2, 3, 4, 5};
        ArrayManipulation.reverseInPlace(original);
        assertArrayEquals(new int[]{5, 4, 3, 2, 1}, original);
    }
```

![Alt text](lab3-1st.png)


### Before
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

### After
```java
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
        int temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
    }
  }
```

For `reverseInPlace`, the fix makes sure the loop only goes through half of the array. It swaps items from the ends towards the middle, using a temporary space to hold an item during the swap. This prevents the program from replacing items incorrectly.

## Part 2 : Using `find` with Options on `./technical`

### 1. **-name**
This option allows you to search for files by name.

 ``` find ./technical/plos -name "*pmed*" ```
```
...
./technical/plos/pmed.0020123.txt
./technical/plos/pmed.0020094.txt
./technical/plos/pmed.0020257.txt
./technical/plos/pmed.0020055.txt
./technical/plos/pmed.0020082.txt
./technical/plos/pmed.0010021.txt
./technical/plos/pmed.0010034.txt
./technical/plos/pmed.0010008.txt
./technical/plos/pmed.0020120.txt
./technical/plos/pmed.0020040.txt
./technical/plos/pmed.0020068.txt
./technical/plos/pmed.0020281.txt
./technical/plos/pmed.0020242.txt 
```

This command will list all files related to `pmed` within the `./technical/plos` subdirectory.


### 2. **-name**
``` find ./technical/plos -name "*journal*" ```
```
...
./technical/plos/journal.pbio.0020439.txt
./technical/plos/journal.pbio.0020404.txt
./technical/plos/journal.pbio.0020148.txt
./technical/plos/journal.pbio.0020028.txt
./technical/plos/journal.pbio.0020216.txt
./technical/plos/journal.pbio.0020206.txt
./technical/plos/journal.pbio.0020010.txt
./technical/plos/journal.pbio.0020164.txt
./technical/plos/journal.pbio.0020400.txt
./technical/plos/journal.pbio.0020401.txt
./technical/plos/journal.pbio.0020213.txt
./technical/plos/journal.pbio.0020013.txt
./technical/plos/journal.pbio.0020172.txt
./technical/plos/journal.pbio.0020012.txt
```
This command helps locate all files related to `journal` within the `./technical/plos` subdirectory, useful for specific document retrievals.

### 3. **-type**
``` find ./technical -type d ```
```
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
```
This command lists every directory within `./technical`, helping you understand the folder structure.

### 4. **-type**
``` find ./technical -type f ```

```
...
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```
(The output is just the last few files output from the command)
This lists all regular files, ignoring directories, links, etc., which is helpful for file-based operations.


### 5. **-mtime**
``` find ./technical -mtime -7 ```

```
...
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```
This command identifies files recently modified within the last week, useful for tracking recent changes. (It showed all the files)
### 6. **-mtime**
``` find ./technical -mtime +30 ```

```  ``` 
This helps identify older files that haven't been modified in over a month. As you can see there was no output.


### 7. **-siza**
``` find ./technical -size -200c ```

```
./technical
./technical/government/Alcohol_Problems
```
Find files smaller than 200 bytes in `./technical`. This is useful for identifying small files.


### 8. **-siza**
``` find ./technical -size +100k ```

```
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Gen_Account_Office/d0269g.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Gen_Account_Office/Sept27-2002_d02966.txt
./technical/government/Gen_Account_Office/d01376g.txt
./technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./technical/government/Gen_Account_Office/pe1019.txt
./technical/government/Gen_Account_Office/gg96118.txt
./technical/government/Gen_Account_Office/d01591sp.txt
./technical/government/Gen_Account_Office/im814.txt
./technical/government/Gen_Account_Office/ai9868.txt
./technical/government/Gen_Account_Office/May1998_ai98068.txt
./technical/government/Gen_Account_Office/d02701.txt
./technical/biomed/1471-2105-3-2.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-12.txt
```
Find files larger than 100KB in `./technical`.This command helps find larger files, which might be consuming significant disk space.


source: [Link Text]([URL](https://www.tecmint.com/35-practical-examples-of-linux-find-command/)) - where I looked to find commands.
