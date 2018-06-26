# Simple-Sed-program-for-one-liner-for-read-trimming
This is a simple sed one liner that can be used for fastq read trimming for fastq files
Sed command to trim reads in fastq file!

sed   '/^@/! { /^+/! {s/^.\{5\}//g;s/.\{75\}$//g;}}' File_name > new_file


This code removes the first 5 and the last 75 characters from the reads and the quality scores in a fastq files.
Explanation:
sed '
         /^@/!  #if line does not start with @ 
         {
             /^+/!  #and line does not start with + ( similar to else if )   
                    {
                         s/^.\{5\}//g; # substitute first 5 characters with nothing .............(1)
                         s/.\{75\}$//; # substitute last 75 characters with nothing ..................(2)
                     }
          }
One can just change the numbers in the the statement (1) and (2) from number of bases to remove.

for more information on sed, please follow the link below.

http://www.pement.org/sed/ifelse.txt
