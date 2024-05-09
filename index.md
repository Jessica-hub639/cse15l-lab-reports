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
