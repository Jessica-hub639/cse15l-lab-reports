#Lab 3
```java
@Test
public void testReverseInPlaceNoFailure() {
    int[] original = new int[]{};
    ArrayExamples.reverseInPlace(original);
    assertArrayEquals(new int[]{}, original);
}
```

