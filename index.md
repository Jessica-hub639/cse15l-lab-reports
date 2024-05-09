#Lab 3

## Test which ends up not a Failure and another that does repectively
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

