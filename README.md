# Test Question and Results


### Task 1: 
Make this work (repeat 3 times the contents of an array):
```javascript
repeat([1,2,3]) //[1,2,3,1,2,3,1,2,3]
```
Your solution:

    function repeat($a) {
      return array_merge($a, $a, $a);
    }
    
### Task 2:
Make this work (no vowels, lowercase except the first letter):
```javascript
reformat("liMeSHArp DeveLoper TEST") //Lmshrp dvlpr tst
```
Your solution:


    function reformat($string) {
        $vowel = ['a', 'e', 'i', 'o', 'u'];
        return ucfirst(str_replace($vowel, '', strtolower($string)));
    }


### Task 3 (optional, for bonus points):
Make this work (without using any built in functions, only a `for` loop, return the next binary number in a string or as an array)
```javascript
next_binary_number([1,0]) // [1,1]

// possible test cases:
// [1,0] => [1,1]
// [1,1] => [1,0,0]
// [1,1,0] => [1,1,1]
// .......
// [1,0,0,0,0,0,0,0,0,1] => [1,0,0,0,0,0,0,0,1,0]
```
Your solution:

    function next_binary_number(array $binary) {
        $binaryDigits = array_reverse($binary);
        $i = 0;
        $decimal = 0;
        foreach($binaryDigits as $binaryDigit) {
            $answer = $binaryDigit * pow(2, $i);
            $decimal += $answer;
            $i++;
        }
        $decimal = $decimal + 1;

        $nextBinaryString = [];
        while ($decimal>=1){
            $leftOver = $decimal % 2;
            $decimal = floor($decimal/2);
            $nextBinaryString[] = $leftOver;
        }

        return implode('', array_reverse($nextBinaryString));
    }
