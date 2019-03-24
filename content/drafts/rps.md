---
title: "My First AI - A Rock, Paper, Scissors Bot "
date: 2017-05-14T00:14:49-04:00
showDate: true
draft: true
tags: ["project"]
---

#### Summary:

* Command line AI that uses your play history to predict your next move in a game of Rock, Paper, Scissors.
* Built in Java.
* Uses Bayesian statistics.

#### Why Did I Build This?
This project was built to showcase an AI technique that I learned from my AI course at the University of Massachusetts, Amherst.

#### How Did I Build This?
This project is built in Java and uses simple Bayesian statistics to predict the player's next move by calculating the probability the player's next move based on all previous moves and based on his/her previous `K` moves.

#### What Did I Learn From Building This?
Through building this, I realized that AI programs can be very simple under the hood. This project took me roughly a day of planning and an entire day of coding, yet performs decently well when facing human players. The reason for this is that humans are actually very bad at generating randomness. Everything we do follows some sort of pattern and one thing computers are good at is keeping track of what the player has done.

#### Operating Instructions:

1. Clone the file.  
`git clone https://github.com/wesleytian/roshambo-god`

2. Navigate to the cloned repository.  
`cd roshambo-god`

3. Compile the file.  
`javac rocpapsci.java`

4. Run the executable where `K` is an integer that represents the short-term memory you want your AI to have. If the value is very large, you will need to play at least `K` rounds before the AI has enough of a history to play you.  
`java rocpapsci <K>`  
Ex:  
`java rocpapsci 2`

5. Continously play rock, paper, or scissors, where 0 represents rock, 1 represents paper, and 2 represents scissors. The AI cannot handle any other input. Remember that you must play at least `K` rounds before the AI has enough history to play you back.  
`<VALUE>`  
Ex:  
```
0  
2  
1
```




GitHub Repo: https://github.com/wesleytian/roshambo-god

