Download Link: https://assignmentchef.com/product/solved-eecs-1015-lab-6-lists-dictionaries-and-tuples
<br>
<strong>          </strong><strong>Lab 6 – Manipulating list of list </strong>

<strong>STARTING CODE LINK</strong>

This lab starts with skeleton code that you can find here: <a href="https://trinket.io/library/trinkets/277a60e993">https://trinket.io/library/trinkets/277a60e993</a>




The starting code defines several global variables (see link above):

<strong># For task 1 </strong>

<strong>rList</strong> = [[1, 10, 9, 4, 50],

[3, 40, 99, 37, 5, 1],

…]

<strong># For task 2 </strong>

<strong>encodedData1</strong> = [[(9, ‘ ‘), (1, ‘.’), …], [(9,’ ‘), (<em>number</em>, <em>character</em>),..]]

<strong>encodedData2</strong> = [[(<em>number</em>, <em>character</em>), (<em>number</em>, <em>character</em>), …], [(<em>number</em>, <em>character</em>), (<em>number</em>, <em>character</em>),..]]




<strong># For task 3 stringData</strong> = “1 H Hydrogen,2 He Helium,3 Li Lithium,4…”

We will explain how these variables will be used below for each Task.

<h1>TASK 1 – Printing and sorting a ragged list</h1>

A “ragged list” is a list of lists where the length of the lists nested inside the main list is not of the same size.

Variable <strong>rList</strong> is a ragged list that has already been defined for you (see above).

For Task 1, you need to implement and call the following two (2) functions:

<ul>

 <li>printRaggedList(param: list) -&gt; no return</li>

</ul>

Loop through each item in the ragged list (which is a list) and print out each list as follows:




Row 0: [item1, item2, item3, …, itemN] Row 1: [item1, item2, …, itemN]

In Python, you can print a list after a formatted string as follows:   print(“format string”.format(arg1, arg2), list)

<ul>

 <li>sortRaggedList(param: list) -&gt; no return (but mutates list)</li>

</ul>

This function will sort each list in the ragged list.   The function should be passed the variable <strong>rList</strong>.




<strong><em>TASK 1 ACTION</em></strong>:

<ul>

 <li>Print the ragged list by passing <strong>rList</strong> as a parameter to printRaggedList().</li>

</ul>




<ul>

 <li>Sort the ragged list by passing <strong>rList</strong> as a parameter to sortRaggedList().</li>

</ul>




<ul>

 <li>Print the ragged list again after sorting using printRaggedList().</li>

</ul>

-We should see that the contents of the lists are sorted.







<h1>TASK 2 – Print an encoded ASCII Art</h1>

This task processes the data in the variables <strong>encodedData1 </strong>and  <strong>encodedData2. </strong>

These variables are bound to a “list of lists of tuples”.  Specifically, each item in the list is another list, that list stores several tuples.

The tuples have two values, the first is a number, the second is a single character.

The tuple is encoding a “run” of characters.  That is the number tells you how many times you could repeat the character.

The idea is that you should “decode” the list of tuples to construct a string that you can print out.  Each list represents  a single line of “Test Art” (or what we call ASCII Art).




See example here:

<table width="671">

 <tbody>

  <tr>

   <td width="192">[ [(5, ‘*’)],</td>

   <td width="48"> </td>

   <td width="96"># row 0</td>

   <td width="335">decodes to: *****  A run of 5 ‘*’</td>

  </tr>

  <tr>

   <td width="192"> [(2, ‘ ‘), (1, ‘*’)],</td>

   <td width="48"> </td>

   <td width="96"># row 1</td>

   <td width="335">decodes to:   *   A run of 2 ‘ ‘, 1 ‘*’</td>

  </tr>

  <tr>

   <td width="192"> [(2, ‘ ‘), (1, ‘*’)],</td>

   <td width="48"> </td>

   <td width="96"># row 2</td>

   <td width="335">decodes to:   *   A run of 2 ‘ ‘, 1 ‘*’</td>

  </tr>

  <tr>

   <td width="192"> [(1, ‘ ‘), (3, ‘*’)]]</td>

   <td width="48"> </td>

   <td width="96"># row 3</td>

   <td width="335">decodes to:  ***  A run of 1 ‘ ‘, and 3 ‘*’</td>

  </tr>

 </tbody>

</table>




To perform this task, define two functions:

<ul>

 <li>decodeTupleList(param: list of tuples) -&gt; string</li>

</ul>

This will take a list of tuples in the form [(number, character), (number, character), …].

You should “decode” the list and its tuples to build a <strong><em>single</em></strong> string.

For example:

decodeTupleList( [ (5, ‘.’), (3, ‘-‘), (5,’.’) ] ) returns “…..—…..”

“.”+”.”+”.”+”.”+”.”  + “-“+”-“+”-”  + “.”+”.”+”.”+”.”+”.” -&gt; “…..—…..”    5 “.” chars           3 “-” chars      5 “.” chars            final string




<ul>

 <li>printEncodedAsciiImage(param: list) -&gt; no return</li>

</ul>

This function will print the ASCII art encoded in lists bound to variables encodedData1 and encodedData2.

When you pass the variable to this function, you should loop through the list.  Recall that each item in the list is another list of tuples.  Call decodeTupleList(item) to decode the string.  decoupleTupleList() returns a string.  Print the returned string. This will print the Ascii Art encoded one line at a time.  When you are done, you should have a nice picture.

In the lab, I will only show you the result of encodedData1 , you have to implement the program to see encodedData2.

<h2>Task 2 ACTIONS</h2>

<ul>

 <li>call printEncodedAsciiImage(encodedData1)</li>

</ul>

-An example of the output of this is shown in the video and in the output below.

<ul>

 <li>call printEncodedAsciiImage(encodedData2)</li>

</ul>

– You need output this too, but it is not shown (you have to implement the task to see it!)













<h1>TASK 3 – Element string to a dictionary</h1>

This task processes the data in the string variable <strong>stringData. </strong>

<strong>stringData </strong>is a long string that encodes the information on the first 25 elements from the periodic table.

To perform this task, define two functions:

<ul>

 <li>buildElementDictionary(param: string) -&gt; dictionary</li>

</ul>

This function processes the <strong>stringData  </strong>to build a dictionary.  The string has the following form.

“1 H Hydrogen,2 He Helium,3 Li Lithium,4 Be Beryllium,5 B Boron,6 C Carbon,…”

Split the string to get a list of each element as follows:

[“1 H Hydrogen”, “2 He Helium”, “3 Li Lithium, …]

Now, for each string in this list, split it to get

“1”, “H”, “Hydrogen”

Add this information to your dictionary as follows:

key=’H’, value = [‘Hydrogen’ ,’1′]  i.e. {‘H’, [‘Hydrogen’, ‘1’]} key=’He’, value = [‘Helium’, ‘2’]   i.e. {‘He’, ‘Helium’, ‘2’]}




Process each element and return the final dictionary with all 25 elements.

<ul>

 <li>printElements(param: dictionary) -&gt; no return</li>

</ul>

This function takes the dictionary created by buildElementDictionary() as a parameter.   Print out the dictionary as follows:

H [Hydrogen] #1             ‘H’ is the key to the dictionary.  Hydrogen and ‘1’ are the 1<sup>st</sup> and 2<sup>nd</sup> items in the list paired with the key.

He [Helium] #2

Li [Lithium] #3

Be [Beryllium] #4

<h2>Task 3 ACTIONS</h2>

<ul>

 <li>Call buildElementDictionary(stringData)

  <ul>

   <li>This will generated the dictionary from the stringData that stores the elements.</li>

  </ul></li>

 <li>Print the dictionary using print().

  <ul>

   <li>Print the dictionary out so its contents and verify that it is OK.</li>

  </ul></li>

 <li>Call printElements() by passing your dictionary.

  <ul>

   <li>This will print out the contents as described above.</li>

  </ul></li>

</ul>

Finally, put all your tasks in the main() function.

main(parameters: none) -&gt; no return

Your main function will be used to test the functionality above.  The skeleton code for your main() is:

def main():

print(“Task 1 – Sorting and printing a ragged list “)          print(“Task 2 – Decoding Ascii Art “)           print(“Task 3 – Elements String to Dictionary “)

<strong>See the next page for an example output of Lab 6. </strong>

Task 1 – Sorting and printing a ragged list

–List before sorting–

Row 3: [2, 9, 44, 88, 100]

Row 4: [2, 4, 9, 19]




Task 2 – Decodng Ascii Art




Task 3 – Elements String to Dictionary

{‘H’: [‘Hydrogen’, ‘1’], ‘He’: [‘Helium’, ‘2’], ‘Li’: [‘Lithium’, ‘3’], ‘Be’: [‘Beryllium’, ‘4’], ‘B’: [‘Boron’, ‘5’], ‘C’: [‘Carbon’, ‘6’], ‘N’: [‘Nitrogen’, ‘7’], ‘O’: [‘Oxygen’, ‘8’], ‘F’: [‘Fluorine’, ‘9’], ‘Ne’: [‘Neon’, ’10’], ‘Na’:

[‘Sodium’, ’11’], ‘Mg’: [‘Magnesium’, ’12’], ‘Al’: [‘Aluminum’, ’13’], ‘Si’: [‘Silicon’, ’14’], ‘P’: [‘Phosphorus’, ’15’], ‘S’: [‘Sulfur’, ’16’], ‘Cl’: [‘Chlorine’, ’17’], ‘Ar’: [‘Argon’, ’18’], ‘K’: [‘Potassium’, ’19’], ‘Ca’: [‘Calcium’, ’20’], ‘Sc’: [‘Scandium’, ’21’], ‘Ti’: [‘Titanium’, ’22’], ‘V’: [‘Vanadium’, ’23’], ‘Cr’: [‘Chromium’, ’24’], ‘Mn’: [‘Manganese’,

’25’]}

Al [Aluminum] #13

Si [Silicon] #14

P [Phosphorus] #15

S [Sulfur] #16

Cl [Chlorine] #17 Ar [Argon] #18

K [Potassium] #19 Ca [Calcium] #20

Sc [Scandium] #21

Ti [Titanium] #22

V [Vanadium] #23

Cr [Chromium] #24

Mn [Manganese] #25

<strong> </strong>


