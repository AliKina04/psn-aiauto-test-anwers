# psn-aiauto-test-anwers

Introduction
=============

Artificial Intelligence used for to simplify and shorten work time if we have a lot of data that we cannot possibly read one by one. 
In this case, how AI calculates how long the device was down referred to by csv data (in second). 
In this process too, my CVS files will be converted into xlsx format to make work easier.

Data Table
===========

This is some of the section data contained in the CVS file. There are 2 columns, namely Epoch Time and Value

| Epoch Time    | Value       |
|---------------|------------ |
| 1704042000000 | 1           |
| 1704042026000 | 1           |
| 1704042035000 | 1           |
| 1704042037000 | 1           |
| 1704042059000 | 1           |

NOTE : <br>
"1" used for the value that means device was down. <br>
"0" used for the value that means device was up. <br>

Explain Code
============
The code starts by initializing a DataFrame df with two columns: 'Epoch Time' and 'Value'. Then, the code iterates over each row of the DataFrame. During an iteration, if the downtime status (is_down) is False and the value in the 'Value' column is 1, then downtime starts, and the start time (start_down) is saved. If is_down is True and the value in the 'Value' column changes to 0 or the iteration reaches the end of the DataFrame, then the downtime ends. The end time (end_down) is saved and the downtime duration is calculated and added to the arrData list. After the iteration is complete, all downtime durations stored in arrData are added up and converted to seconds, then the results are printed.
