# Expression Calculator
This project contains a calculator that gets an input number from the user and applies the bellow formula to it. Assuming the given number is 38, the calculation will be:

&nbsp;

![image](https://user-images.githubusercontent.com/61691909/165219835-d083e03c-6ee0-4904-843c-53d02ec38f57.png)

&nbsp;

As noted in this formula, the sign is intercalated. That means that the first one is making a sum, while the second is subtracting, and so on until it reaches the smallest expression possible. For that reason, I determined that the number entered by the user must be greater than or equal to 2, because other than that it wouldn't be possible to make this calculation. Therefore, I created an if statement to make this validation, and if the result is false the program simply ends with the message: "Invalid number!".

After verifying that the number is greater than or equal to 2, the variable **j** receives the number, serving as a variable to store it as the initial value, and then it's going to be decremented with each iteration since the expression is getting reduced. On the other hand, there is the **i** variable, that gets incremented within the for loop, starting with 1 and going until it reaches the number given by the user minus 1. Therefore, the **i** variable is used as the divider of this formula, while controlling the number of iterations of the for loop.

As I want to display to the user each step of the calculation, I created the variable **currSum** inside the scope of the loop. In each iteration of the loop, this variable is going to store the current value of the total result before it changes again, in order to show to the user the previous value being calculated with the new value that was generated by the formula. I'm also going to show the expression used to calculate in each step, but I want it properly formatted to be displayed. The final result will be displayed using the format I created with the DecimalFormat class, so I'm going to apply this format to the expression as well. As for the variables **j** and **i**, they were declared as **double** to guarantee that the result will be as precise as possible. I don't want do display values like "38.0", since the user didn't type it that way, it would be weird. Therefore, I'm also adding a format to these numbers when they are being displayed, using the method **round()** of the Math class to round them.

Next, I put a 2 second pause because I want the information being displayed one by one instead of appearing all at once on the screen. Then, I display on the screen the formula being used and the result of this calculation.

For the sum, I use an if statement asking if the value of the **i** variable is equal to 1 or is an even number. I do this because the sign is only positive in one of these two conditions. Therefore, if one of these conditions are true, we enter the if scope where the result of the formula is being summed to the value of the variable **newSum**. To show it to the user, I also create variables in which there will be the formatted values of the previous result and the new result. Then, I display the calculation being made again. If it enters the else scope, I simply subtract instead of summing, and display the values the same way. At the end of the for loop, the value of **j** is decremented.

Finally, I display the final result using the final formatted variable. I also have a try/catch block surrounding most of this code, because the Scanner class can throw an exception if the value entered is not a number, so I want to treat this exception properly.
