
Part 1:

Original code:


```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
Junit Test 
```
@Test 
public void testReverseInPlace1() {
    int[] input1 = {5,6,7};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{7,6,5}, input1);
    
	}

1 out of 1 tests, failed. Failure happened as testReversedMultiple(), where expected array {4,3,2,1} but got {4,3,3,4}.

```

input that doesn’t induce a failure
```
    @Test 
    public void testReverseInPlace1() {
        int[] input1 = {5,6,5};
        ArrayExamples.reverseInPlace(input1);
        assertArrayEquals(new int[]{5,6,5}, input1);


JUnit version 4.13.2
.....
Time: 0.008

OK (5 tests)    
```


The symptom:




 ![Image](L3-1.PNG)





Before and After :
```
//before

static void reverseInPlace(int[] arr) {
    

    for(int i = 0; i < arr.length; i = i+1) {
       
      arr[i] = arr[arr.length - i -1];
      
    }
  }

//after
static void reverseInPlace(int[] arr) {
    int arrt[]=arr.clone();

    for(int i = 0; i < arrt.length; i = i+1) {
       
      arr[i] = arr[arr.length - i -1];
      
    }
  }
```
The fix adresed the issue that the original array was writing over itself with iteself. i fixed thi by copying the array to a new array and useing that to overwrite the original array.

 
