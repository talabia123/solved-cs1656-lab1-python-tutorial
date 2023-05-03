Download Link: https://assignmentchef.com/product/solved-cs1656-lab1-python-tutorial
<br>



In this lab, you will learn file I/O, JSON files, and CSV files in Python. Packages you will need are:

<ul>

 <li>os</li>

 <li>csv</li>

 <li>json</li>

</ul>

<strong> </strong>

<h1>Part 1: File I/O</h1>

Reading and writing text files is typically very straightforward. Here is an overview of file I/O in Python.

<ol>

 <li><strong>Getting input filename from command line </strong>file_in = input(‘Enter name of input file: ‘)</li>

</ol>




<ol>

 <li><strong>Checking if file exists and manipulating pathnames </strong><strong>if </strong>path.isfile(os.path.join(os.getcwd(),file_in))</li>

</ol>

<h2>c. Open/Close and modifying file position</h2>




<table width="492">

 <tbody>

  <tr>

   <td width="172">f = open(file_in) <strong>print (</strong>f.tell())  f.read(1)f.readline()f.seek(-3,2)f.seek(0)f.close()</td>

   <td width="320"><em># current position </em><em># read one byte and move forward </em><em># get bytes from the file until newline </em><em># move back 3 characters before the end </em><em># move back to beginning of file </em><em># important if writing to file</em></td>

  </tr>

 </tbody>

</table>

Another way of opening the file is to use <em>with</em> statement. The use of with statement establishes a context in which the file will be used and when control leaves the with block, the file will be closed automatically. You don’t need to use the with statement, but if you don’t use it, make sure you remember to close the file. <strong>with </strong>open(file_in,<strong>“r+”</strong>) <strong>as </strong>f:

<strong>print (</strong>f.tell())

<h2>d. Read/Write to Files</h2>

There are several ways of reading and writing to files in Python. Here we show some of them.

One way of reading the file is:  read_data = f.<strong>read</strong>() An alternate way of reading line by line by iterating over the file is:   <strong>for </strong>line <strong>in </strong>f:       <strong>print</strong>(line)

In order to write to a file,

f.writelines(<strong>“Yay! Written to file on Friday, 9/9/16 &#x1f600; </strong><strong>
</strong><strong>“</strong>)

<strong> </strong>

<h1>Part 2: JSON</h1>

JSON file format is used to save generic data programmatic data structures as strings and is commonly used for serialization. JSON is good for storing simple data structures into text file and sending data to other people.

zipCodes = [60290,60601,60602,60603,60604,60605,60606]

<em># dump into a file </em>f = open(<strong>‘example2.json’</strong>,<strong>‘w’</strong>) json.<strong>dump</strong>(zipCodes,f)

f.close()

<em># load back into Python </em>f = open(<strong>‘example2.json’</strong>,<strong>‘r’</strong>) zipCodes2 = json.<strong>load</strong>(f)

f.close()

<em># compare </em>

<strong>print(</strong><strong>“Checking zipcodes…”</strong>) <strong>print</strong>(zipCodes == zipCodes2)




<h1>Part 3: JSON / read</h1>

In this example, we will download a JSON file from a URL and display the file one line at a time.

<strong>print</strong>(<strong>‘Downloading JSON file and printing entire file:’</strong>) response = <strong>get</strong>(<strong>‘http://data.cs1656.org/hours.json’</strong>) <strong>print</strong>(response.content)

<strong>print</strong>(<strong>‘Loading as JSON and iterating one line at a time:’</strong>) hours = json.loads(response.content) <strong>print</strong>(hours)

<strong>print</strong>(<strong>‘
Iterating over JSON:’</strong>) <strong>for</strong> line <strong>in</strong> hours:     <strong>print</strong> (line)

<strong>           </strong>

<h1>Part 4: Convert to CSV – On your own</h1>

For the next task you need to write a python program to convert the JSON file (downloaded from Part 4) into a CSV file that you need to save to disk. To do this you should look up the <strong>csv module</strong> and the <strong>writer()</strong> function in particular.




<h1>Part 5: Read CSV – On your own</h1>

For the next task you need to write a python program to read the CSV file from disk and display its raw contents (without recognizing rows or fields).




<h1>Part 6: Read from CSV / rows – On your own</h1>

For the next task you need to write a python program to read the CSV file from disk and display its contents one row at a time (without recognizing fields).




<h1>Part 7: Read from CSV / cells – On your own</h1>

For the next task you need to write a python program to read the CSV file from disk and display its contents one row at a time and then, within each row, one field at a time


