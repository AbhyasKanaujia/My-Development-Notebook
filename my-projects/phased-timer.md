# ⏲ Phased Timer

## Log

| Day                 | Progress                                                         |
| ------------------- | ---------------------------------------------------------------- |
| Day 1, 27 June 2022 | Created GitBook. Add inspiration, motivation, plan, and design.  |
|                     |                                                                  |
|                     |                                                                  |
|                     |                                                                  |

## Inspiration&#x20;

This is an app inspired by the [Pomodoro Technique](https://en.wikipedia.org/wiki/Pomodoro\_Technique). It's a technique that helps you stay focused by letting you work for 25 minutes (work time), then have a break for 5 minutes (short break). After 3 such sessions, you get a 15 minutes break (long break). I'm using it right now as I work on this project. The pomodoro technique is great and has actually helped me focus better while avoiding burning my self out.&#x20;

I want to create an app where instead of having 3 phases like in the pomodoro technique: work time, short break and long break, I'd like to be able to define my own phases.&#x20;

### Apps:&#x20;

#### [https://pomofocus.io/](https://pomofocus.io/)

This app has some really great features. Too many, I must say, for what I'm for.&#x20;

#### [https://pomodoroproject.io/](https://pomodoroproject.io/)

This app has a really beautiful minimalistic design. I want to go for something like this.&#x20;

## Motivation

Right now, I'm practising coding for technical interviews. Sometimes I spend too much or too little time on things like reading the question, trying it out, coding, dry run etc. I want to distribute it such that I'm spending: 5 min on reading the question, 10 minutes on trying it out, 10 more on coding and if the solution doesn't work dry run it for 5 minutes and code it once more before moving to the solution.&#x20;

This app will help me spend the right amount of time on each “phase.”

## Plan

I've noticed that every time I start a project, I abandon it midway. The main reason is that either:

* I'm not satisfied by the look of the app
* I spend too much time thinking about how it will look and never get to reach the part when I am actually building the functionality.

Then I'm exhausted and bored long before I read this point.&#x20;

So this time I'm going to build this whole thing in bare-bones HTML. I'll build the functionality and let the design be optional this time. I found this piece of CSS called [100 Bytes of CSS to look great everywhere ](https://www.swyx.io/css-100-bytes)from [my friend's digital garden](https://notes.whoibrar.com/2022/04). Now I've applied that, and I'm hoping this will look decent enough.&#x20;

## Design

### Basic

#### Main Screen

* The main screen will show the phases that have passed, the current phase and the upcoming phase.&#x20;
* The current phase will be pronounced and will have its timer running.&#x20;

#### Edit Screen

* Shows a list of label and duration.&#x20;
* `Edit` and `delete` button
* `Add` below and add above button.&#x20;

### Advanced

#### Main Screen

* The page will automatically scroll to keep the current time within the frame.&#x20;

#### Edit Screen

* A `move up` and `move down` button for items in the list.&#x20;
