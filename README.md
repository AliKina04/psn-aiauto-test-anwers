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

Epoch Time
===========
![image](https://github.com/user-attachments/assets/973e7393-8351-47bd-9e98-44cdff9ef91f)

Epoch Time is date and time representations are widely used in computing. It measures time by the number of seconds.

Process Code
============
The code starts by initializing a DataFrame df with two columns: 'Epoch Time' and 'Value'. Then, the code iterates over each row of the DataFrame. During an iteration, if the downtime status (is_down) is False and the value in the 'Value' column is 1, then downtime starts, and the start time (start_down) is saved. If is_down is True and the value in the 'Value' column changes to 0 or the iteration reaches the end of the DataFrame, then the downtime ends. The end time (end_down) is saved and the downtime duration is calculated and added to the arrData list. After the iteration is complete, all downtime durations stored in arrData are added up and converted to seconds, then the results are printed.

![image](https://github.com/user-attachments/assets/c55530a6-0c76-4faa-aaf2-49f2a4c99e60) <br>
Explain : <br>
1. Recreate the df DataFrame with only the Epoch Time and Value columns included. <br>
2. x = 0: Initialize the variable x as a counter used to iterate through the DataFrame. <br>
3. "is_down = False:" Initialize the boolean variable is_down to track the status (whether there is downtime or not).<br>
4. "arrData = []:" stores the downtime duration.<br>
5. The loop runs as many times as there are rows in the DataFrame df.<br>
6. Checking whether is_down is False. If False, it means the system is not in downtime.<br>
7. If the Value value is '1', then set is_down = True (indicating that downtime is in progress) and save the downtime start time (start_down) with the value 
   from df['Epoch Time'][x].<br>
8. "is_down" is True, meaning downtime is in progress.<br>
9. DataFrame (x == len(df) - 1). '0' indicates that downtime has ended.<br>
10. Calculate the total downtime by adding up all the elements in arrData, adding pd.Timedelta(0) as the time initialization. The results are converted to seconds 
    with total_seconds().
