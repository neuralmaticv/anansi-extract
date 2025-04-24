# Anansi Extract - Documentation

## Table of Contents

- [Anansi Extract - Documentation](#anansi-extract---documentation)
  - [Table of Contents](#table-of-contents)
  - [Idea \& Motivation](#idea--motivation)
    - [Reason #1](#reason-1)
    - [Reason #2](#reason-2)
  - [Results - extracted questions \& answers](#results---extracted-questions--answers)
    - [Slagalica (more than 24k questions and answers)](#slagalica-more-than-24k-questions-and-answers)
    - [Pot(j)era (3k questions and answers)](#potjera-3k-questions-and-answers)
  - [Algorithm](#algorithm)
    - [General idea](#general-idea)
  - [Optimisation ideas](#optimisation-ideas)
  - [Future Roadmap](#future-roadmap)
  - [Known problems](#known-problems)
  - [How to run scripts locally](#how-to-run-scripts-locally)

## Idea & Motivation

There are two main reasons for doing this project.

### Reason #1
In the last couple of years, the pub quiz scene in Serbia has seen a rise in popularity. After doing a bit of research and after competing myself in some of the quizzes, I saw that a lot of questions are recycled and that it would be nice if there was some kind of a "knowledge database" where you can test yourself and perhaps prepare yourself for the quizzes. 

To my surprise, I found that there are only a couple of popular mobile/browser games that mimicks popular games from the TV shows, but are very limited when it comes to the actual distinct number of questions that they have in their databases. 

I found that a lot of questions used in the pub quizzes are from TV game shows, so, naturally, I started watching the episodes of Slagalica (Serbian), Potera (Serbian), and Potjera (Croatian), however, that took too long. Episodes of Slagalica are 22mins and Potera (eng. The Chase) is more than 40mins long. And the most fun games in both of them are games where you can directly test your knowledge - in Slagalica game is called "Ko zna zna" and in Potera, I think it does not have a name officially, it's always being referred to as the "second game" :). 

So after giving it some thought, I decided to create a program that will go through the episodes, find the games, extract the questions, find the answers and put all of that in some spreadsheet-friendly format such as ".csv". 

After a couple of days, this is the project that I come up with. 

### Reason #2
Learn something new. I've never, not since college anyway, done any computer vision work, and I didn't have any experience with OCRs too. So it was a really nice opportunity to venture into the unknown.

## Results - extracted questions & answers

### Slagalica (more than 24k questions and answers)
[https://tinyurl.com/anansi-slagalica](https://tinyurl.com/anansi-slagalica)

### Pot(j)era (3k questions and answers)
[https://tinyurl.com/anansi-pot(j)era](https://tinyurl.com/anansi-potera)

**Note:** Slagalica has a lot more (24k > 3k) questions extracted simply because the Slagalica TV show has an [official youtube channel](https://www.youtube.com/channel/UCPYHhBsZpnBFOiiM5mfDf9w) where all recent episodes can be found. Pot(j)era does not have an official channel, and videos are often removed due to copyright infringements which in result leads to a very limited number of episodes circulating on the internet.

## Algorithm

The following sections explain how everything works under the hood.

### General idea
In both Slagalica and Pot(j)era, the main idea is the same:

1. Open the video file
2. Find the beginning of the desired game
3. Recognize the frame where both question and answer are visible
4. Extract sections of the frame with the texts and preprocess them for OCR
5. OCR the sections to get questions & answers
6. Move to the next question
7. Finish processing the video file if the game has ended

For detailed algorithm explanations, please refer to:
- [Slagalica Algorithm](./docs/algorithm_slagalica.md)
- [Pot(j)era Algorithm](./docs/algorithm_potera.md)

## Optimisation ideas
[See detailed optimisation ideas](./docs/optimisation.md)

## Future Roadmap
[See detailed roadmap](./docs/roadmap.md)

**Note**: Certain features from the original roadmap have been intentionally excluded or reconsidered due to potential copyright concerns.  
TV quiz shows are copyrighted works, and the questions themselves may be protected under copyright law.  
This project aims to remain within fair use and ethical boundaries, and is intended strictly for educational and research purposes.


## Known problems
[See known issues](./docs/known_issues.md)

## How to run scripts locally
[See installation and usage guide](./docs/installation.md)
