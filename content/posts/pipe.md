---
title: "Super Linux Warp Pipe"
date: 2018-07-24T00:14:49-04:00
showDate: true
draft: true
tags: ["blog","story"]
---

Today at work I came across a problem that managed to solve using the Linux pipe. The problem was that I wanted to count the frequency of words between a certain fixed context.

This is a simplified version of what the input looked like:

---
	Where is the { FRUIT apple } ?
	Is the { PLANT tree } within the ground ?
	The { FRUIT banana } ate some { FRUIT banana } .
---

If I wanted to look for the frequency of words only with the `FRUIT` label, then the intended output should look like:

---
	2 banana
	1 apple
---

To prevent a breach of confidentiality, I have replaced the actual words with something else.

The command that I ended up doing the trick was:

---
	cat input_file | grep -o -P '(?<={ SPENDABLE).*?(?= })' | grep -v "^\s$" | sort | uniq -c | sort -bnr > output_file
---

Below, I will break down what each part does. I will cover the following commands and flags: `grep -o -P -v`, `sort -bnr`, `uniq -c` as well as the Perl regular expression (regex).
