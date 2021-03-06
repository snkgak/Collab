# AUTO Mechanical Analysis Protocol

This is the how-to guide for using the batch-process mechanical testing analysis [MATLAB](https://www.mathworks.com/products/matlab.htmlcodei "MATLAB homepage") code, `AUTO_mech_prop_bbml.m`, which is used to analyze force displacement data from mechanical tests.

**FOLDER SETUP**

Place the following files in one folder.

| File                                                         | Naming Convention                                            | Error if wrong                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| *CT\_geom\_avg.xlsx*, (generated by cortical MATLAB code)    | No convention for the file itself, but all specimens in the first column of the ‘RAW DATA’ sheet must match the mechanical test file name. (This allows alpha-numeric specimen names). E.g., if mech file is ‘239A\_RT.csv’, the specimen name listed must be ‘239A\_RT’. | Code will print “Mechanical data not found for ‘List value’.” for every value that does not have a corresponding mechanical file. |
| Mechanical test data generated by BOSE                       | No naming convention, but must be ‘.csv’ files.              | Code will print “Mechanical data not found for ‘List value’.” if a different file format is used. |
| *AUTO\_mech\_prop\_bbml.m* (MATLAB code, copy and paste from protocol folder) | N/A                                                          | N/A                                                          |

**RUN THE CODE **

1.  Double-click *AUTO\_mech\_prop\_bbml.m* to open it in MATLAB.

2.  Go to line 73 in the code and change the testing configuration in
    the file to match your setup.

![](1.png){width="6.45in" height="2.6166666666666667in"}

1.  Run the MATLAB file (can do with green play button at the top). The
    dialogue box shown below will pop up to prompt you to confirm that
    you have edited the testing configuration values.

![](2.png){width="3.466666666666667in"
height="1.2166666666666666in"}

> Click “Yes” to start the code, “No” to go back and edit, and “Huh?” to
> get an explanation of where in the code you need to edit values.

1.  After you click “Yes”, you’ll be prompted to choose the file with
    the CT geometry data.

    A.  Double click the file with the cortical data

    B.  OR click the file with the cortical data, then click Open

![](3.png){width="6.5in" height="4.331306867891514in"}

1.  The code will now analyze all specimens listed in your CT\_geom
    file. It takes 1-2 sec to analyze each specimen, so the
    batch-process should go quickly.

**CHECK CODE OUTPUT**

1.  When the code is done running it will display:

> ![](4.png){width="5.666666666666667in"
> height="0.7916666666666666in"}
>
> (Elapsed time will vary)
>
> This is a reminder to check that the code has properly analyzed the
> data. TO ENSURE ACCURATE RESULTS, IT IS HIGHLY RECOMMENDED THAT YOU
> CHECK BOTH OUTPUT PLOTS FOR EACH SPECIMEN. If you believe either plot
> output is wrong, re-run that specimen using an old manual code,
> *Mech\_prop\_bbml.m* OR *bend\_bose\_excelgeom\_fc.m*.

1.  For the COMP plot (sample shown below), check that the adjusted data
    set (shown as a solid black line) is the correctly truncated and
    zeroed version of the original data set (shown as a dashed line).

![](5.png){width="5.833333333333333in" height="4.375in"}

1.  For the stress/strain plot (sample shown below), check that the
    modulus line is truly parallel to the elastic region, and that the
    yield, maximum, and failure points look correct.

![](6.png){width="5.833333333333333in" height="4.375in"}

Note: *AUTO\_mech\_prop\_bbml.m* has been optimized for the standard
displacement rate used in the Wallace lab, **0.025 mm/sec**. If your
displacement rate is several orders of magnitude larger or smaller than
that, you will likely get inaccurate results. If so, contact
<rachkohl@iu.edu> for help in optimizing to your setup, or use a manual
code (*Mech\_prop\_bbml.m* or *bend\_bose\_excelgeom\_fc.m)* instead.
