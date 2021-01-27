# LG-wrangle
## Word Searching in Mcbeth
* play: [MacBeth] ("http://shakespeare.mit.edu/macbeth/full.html")
* speaker 1: Macbeth
* speaker 2: MacDuff
* Question: How many times did MacBeth speak? How many times did MacDuff speak? What was the sum?

Steps:
1. Find the play and pull it into a text fill. Is use sed command to remove the html or extra stuff besides the play
'''bash
curl "http://shakespeare.mit.edu/macbeth/full.html"|sed 's/<\/*[^>]*>//g' > play.txt
'''
1. Now that I have the play i need to find out how much speaker 1 on talks or macbeth and save it into a file which will be used later
'''bash
 grep '^MACBETH$' play.txt -c >macbethSpeaks.txt
'''
1. And Repeat for speaker 2 or macduff. I will create a diffrent fill for it
'''bash
 grep '^MACDUFF$' play.txt -c >macduffSpeaks.txt
'''
1. To find the sum I will list out all the times MACBETH speaks
'''bash
 grep '^MACBETH$' play.txt >macbethandmacduffSpeaks.txt
'''
1. Then I will add on MAcDuff using the same process
'''bash
 grep '^MACDUFF$' play.txt >>macbethandmacduffSpeaks.txt
'''
1. The file is not very useful but the count of the file is
'''bash
 grep '^MAC' macbethandmacduffSpeaks.txt -c > sumSpeaks.txt
'''

## Anwser
The total number time they both speak is 205. I thought it would be more.