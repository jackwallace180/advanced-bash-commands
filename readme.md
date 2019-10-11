# advanced bash notes :bacon:

## Linux is extensionless
 .txt means NOTHING

 ## Everything is a file

 dont use spaces in files/directorys and always lower case

 man ls = view manual

 ls .jpg    will list only jpgs
 ls example?.txt   will show all files with a character in ?

 ls * AMAZING

 ## linux permissions

 things a user can do
 read (r) write (w) and execute (x)

 users that exist are
 - owner
 typically the person/user who create the file. however this can be changed     
 -group
 every file belongs to a single group. Groups have many users in it and give access to multiple people
 - others
 everyone else not in a group or the owner.

 ## view permissions

 ll == long list

 on lhs you will see something like rwx x3 (all users can r w x)

 ### changing permissions

 chmod permissions file/path
 - example --> chmod g-x example.txt
 will remove execute permission from a group user in file example.txt

 head -3 file
 tail -4 file

 this give you the top 3 lines and bottom v4 lines for a files

 sort file will sort is alphabetically

 nl file will count the number of lines

 ## STREAMS REDIRECT AND PIPING

 stream is a flow of data

 ### STREAMS
 - stdin    standard input   code is 0
 - stdout     standard output   code is 1
 - stderr     standard error   code is 2

 ### piping in REDIRECT

 meand we can join all these amazing commands together :)

## redirecting
### this is redirecting of stdout
 ls > file     will put the list short print into the file

 wc file > word_count.txt    will put the word count of the file into a word_count.txt files

cat file >> word_count.txt will append the print to the end of word_count files

### stdin
wc -1 < words.txt

### stderr

ls missing_directory 2> ls_log.txt   will log the error into the file ls_log.txt, the error here is the directory does not exist so cannot be listed (you need the 2 to log the error)

## piping = |

we sent STDOUT and STDERR into files, but what we want is to be able to send outputs into toher programs. this is very powerful and is called piping :taco:

we use the | to join programs

for example
 - ls | head -2 will list the first 2 files
 - ls | tail -2 > last_two_files.txt   will output the last 2 file names into a file named last_two_files.txt

 grep <word>   this is a prgram that searches for you word and shows you all instances

 cat example.txt | grep it   this will find all lines in example.txt with 'it' in it

 #### running the instance of a program is called the process, we can do multiple processes at the same

 ## process management

 top
 will show your your processes live with most cpu intensive at the top

 ps
  - will show your user processes

 ps aux
 - shows all processes


 you can get a PID (process id) from your ps

 then use kill <PID> to terminate the process

 #### sending processes to the background

 sleep 100 will sleep your machine for 100 seconds (foreground)

 sleep 100 & will send this sleep to the background (basically wont do anything but can be viewed by ps aux)
