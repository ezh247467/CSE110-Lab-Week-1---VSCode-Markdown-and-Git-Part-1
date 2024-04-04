# Ethan's User Page
## Introduction
Hello, my name is Ethan Huang and I am a third-year Computer Science student. I enjoy learning about [software tools](https://ezh247467.github.io/CSE110-Lab-Week-1---VSCode-Markdown-and-Git-Part-1/#favorite-commands) like **Git** and **bash**, specifically the numerous commands I can use for them. I also like to look at different coding algorithms and try to code them out myself. For algorithms that are bit too hard for me to implement reliably, I like to just read the working code of them on the internet and see how well I can trace the code.

One of my absolute favorite things to eat are the Habanero wings from Dirty Birds with extra sauce.
![My favorite food](./images/habanero-hot-wings.jpg)

I don't have an image of them myself so this is the best thing I can find from the internet :(
## Favorite Quote
Alan Turing a person that I look up to and as someone who expresses immense interest in AI and loves the idea of the Turing Test, my favorite quote from him has to be:
> A computer would deserve to be called intelligent if it could deceive a human into beliving it is a human.

## Favorite Sorting Algorithm: MergeSort
This is my own implementation of MergeSort from what I can remember (CSE12 was so long ago for me!) in C++ *(my friend Joshua created the test cases)*.

```
#include <iostream>
#include <vector>
#include <cassert>
using namespace std;

typedef unsigned int uint;

vector<int> MergeSort(vector<int> arr) {
	if (arr.size() <= 1) {
		return arr;
	}
	uint half = arr.size() / 2;
	vector<int> left_h(arr.begin(), arr.end() - half);
	vector<int> right_h(arr.end() - half, arr.end());

	// Split the vectors in half recursively.
	vector<int> left = MergeSort(left_h);
	vector<int> right = MergeSort(right_h);	

	int i = 0, j = 0;
	vector<int> result;
	// Populate vector in order.
	while (i < left.size() && j < right.size()) {
		if (left[i] < right[j]) {
			result.push_back(left[i++]);
		} else {
			result.push_back(right[j++]);
		}
	}
	// Fill the rest of the vector with the remaining elements.
	while (i < left.size()) {
		result.push_back(left[i++]);
	}
	while (j < right.size()) {
		result.push_back(right[j++]);
	}
	return result;
}

int main() {
	// Normal Case: 5 Ints from 1-5.
	vector<int> normal = {4,3,1,2,5};
	vector<int> normalAns = {1,2,3,4,5};
	assert(MergeSort(normal) == normalAns);
	// Duplicate Case: 5 Ints of the Same Number.
	vector<int> dupe = {2,2,2,2,2};
	vector<int> dupeAns = {2,2,2,2,2};
	assert(MergeSort(dupe) == dupeAns);
	// Negative Case: 5 Ints with Negative and Positive
	vector<int> neg = {6, 3, -2, -10, 15};
	vector<int> negAns = {-10, -2, 3, 6, 15};
	assert(MergeSort(neg) == negAns);
	// Single Case: 1 Int.
	vector<int> one = {5};
	vector<int> oneAns = {5};
	assert(MergeSort(one) == oneAns);
	vector<int> ref = {};
	// Populate vector with random numbers.
	for (int i = 0; i < 10000; i++) {
		int num = rand() % 50000;
		ref.push_back(num);
	}
	vector<int> stressAns = ref;
	sort(stressAns.begin(),stressAns.end());
	assert(MergeSort(ref) == stressAns);
	// Zero Case
	vector<int> zero = {};
	vector<int> zeroAns = {};
	assert(MergeSort(zero) == zeroAns);

	vector<int> ref2 = {};
	// Populate vector with random numbers.
	for (int i = 0; i < 1000000; i++) {
		int num2 = rand() % 50000000;
		ref2.push_back(num2);
	}
	vector<int> stressAns2 = ref2;
	sort(stressAns2.begin(),stressAns2.end());
	assert(MergeSort(ref2) == stressAns2);
	return 0;
}
```

## Favorite Commands
As I've stated before, I love learning about the different commands that can be used on the command line/terminal as well as other software tools I've learned from my experience at UCSD ***(thank you CSE15L!)***. The commands I will be listing will be separated by software tool
1. **Bash/Command Line**
   - ```find``` - I like using this command for finding a specific file or all files with a certain extension.
   - ```grep``` - I don't use it very often but it's extremely helpful when I'm trying to figure out what files had a certain key word I was using.
   - ```vim``` - My favorite text editor to call and probably my most used command.
2. **Vim**
   - ```"+y``` - Copying to the system clipboard through Vim has always been a gamechanger! There are times that I just want to quickly copy something from my trusty editor and straight to somewhere else.
   - ```:ter``` - Since I just love using the command line so much, nothing makes me happier than to use both Vim and the terminal at the same time! However, I like my terminal to be side by side with my Vim editor.
   - ```:vsp``` - My current best solution to getting the terminal to appear side by side with my Vim editor. A vertical split to create a second Vim editor on the side then using the ```:ter``` to get the terminal there. I can then quit out of the extra Vim editor and *voilà*!
  3. **Git**
     - ```git stash``` - There are times when I forget to pull before starting. When I stage and commit my changes, I get told that I'm currently I'm too many commits behind? Stashing my changes have been a lifesaver since it's just a pain to rewrite my changes.
     - ```git reset``` - There have been many times that I committed something that I probably shouldn't have. Reseting the HEAD pointer has been a gamechanger for me!
     - ```git restore``` - Just like with above, there are times that I staged files that I didn't mean to stage (sometimes I just get lazy and just do ```git add .``` without checking status) so thank goodness I can unstage files!


- [x]  Finish [README file](README.md)
- [x]  Add Section Links
- [x]  Finished Lab 1

