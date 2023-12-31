# Extract-PSImage
A tool to extract Powershell script from PNG image generated by Invoke-PSImage.  
Note: This is a beta version. I am planning to make improvements. 

## Description
Extract a PowerShell script in the PNG file generated by **Invoke-PSImage**.  

About *Invoke-PSImage*, please see [here](https://github.com/peewpw/Invoke-PSImage). 　

Extract-PSImage is a PowerShell script.   
You should specify two params : The path to the PNG image, and the path to the file to output the extracted Powershell script.  

Extract-PSImage extracts the Powershell script string of the maximum length that the image file may contain.  
So there is 2 limitations.  
->If the embedded script is shorter than the maximum length, a random padding string is extracted after the script.  
->Even if there is no embedded script in the image, The Extract-PSImage process looks like it succeeded. But there is no valid output.
 (Only meaningless strings are output.)

I think if you look at the first 50 characters of output, you can determine if the script has been extracted or not.

## Arguments
-Image [filepath] The path to the PNG image which you want to analyze.

-Out [filepath] The file to save the extracted Powershell script ( to the .ps1 file).

## Usage
PS> Import-Module .\Extract-Invoke-PSImage.ps1  
PS> Extract-Invoke-PSImage -Image [path to the PNG image] -Out [path to the .ps1 file]  
[Oneliner to extract embedded payload]  
[First 50 characters of extracted payload]  

## Example
Under the sample folder, I prepared two examples.
![Extracting payload](https://github.com/imurasheen/Extract-PSImage/blob/master/extract_payload.png)

## Issue
1. Add the argument : -Length  
To specify the length to extract the Powershell script.  
2. Add the argument : -Web  
To specify the image file by URL  

## Licence
[MIT](https://github.com/tcnksm/tool/blob/master/LICENCE)

## Author
[imurasheen](https://github.com/imurasheen)  
[blog](https://imurasheen.hatenablog.com/)  
