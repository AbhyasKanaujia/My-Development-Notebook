# ⏲ Phased Timer

## Log

| Day                 | Progress                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Day 1, 27 June 2022 | Created GitBook. Add inspiration, motivation, plan, and design.                                                                                                                                                                                                                                                                                                                         |
| Day 2, 28 June 2022 | <p>I don't have time to work on this project since I'm preparing my interviews. So I'll work on this whenever I get a break from my current pomodoro. <br><br>This project is too ambitious, and I think I'll benefit more from building something simple and them coming back to this. I'll take a break from this. <br><br>I'm not able to handle events or pass props properly. </p> |
|                     |                                                                                                                                                                                                                                                                                                                                                                                         |
|                     |                                                                                                                                                                                                                                                                                                                                                                                         |
|                     |                                                                                                                                                                                                                                                                                                                                                                                         |
|                     |                                                                                                                                                                                                                                                                                                                                                                                         |
|                     |                                                                                                                                                                                                                                                                                                                                                                                         |

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

Then I'm exhausted and bored long before I reach this point.&#x20;

So this time I'm going to build this whole thing in bare-bones HTML. I'll build the functionality and let the design be optional this time. I found this piece of CSS called, [100 Bytes of CSS to look great everywhere](https://www.swyx.io/css-100-bytes) from [my friend's digital garden](https://notes.whoibrar.com/2022/04). Now I've applied that, and I'm hoping this will look decent enough.&#x20;

I'll also mark the features as advanced so that I don't get distracted by them. I need to get the [MVP](https://en.wikipedia.org/wiki/Minimum\_viable\_product) down first.&#x20;

## Design

### Screens

#### Main Screen

* The main screen will show the phases that have passed, the current phase and the upcoming phase.&#x20;
* The current phase will be pronounced and will have its timer running.&#x20;
* **\[Advanced]** The page will automatically scroll to keep the current time within the frame.&#x20;

#### Edit Screen

* Shows a list of label and duration.&#x20;
* `Edit` and `delete` button
* `Add` below and add above button.&#x20;
* **\[Advanced]** A `move up` and `move down` button for items in the list.&#x20;

### Components

#### Main Screen

<img src="../.gitbook/assets/file.drawing.svg" alt="Component Tree for Main Screen" class="gitbook-drawing">

## States of each task

* Incomplete/Complete
* Active/Inactive
* Running/Paused

<img src="../.gitbook/assets/file.drawing (1).svg" alt="" class="gitbook-drawing">

## Database&#x20;

I'm going to use the local storage as the database and store it as a JSON.

Here's the structure I'm thinking of:&#x20;

```json
export const phases = [
  {
    _id: 1,
    name: "Read Question",
    time: 300,
    elapsed: 300,
    completed: true,
    active: false,
    current: true,
  },
  {
    _id: 2,
    name: "Attempt",
    time: 600,
    elapsed: 300,
    completed: false,
    active: true,
    current: true,
  },
  {
    _id: 3,
    name: "Dry Run",
    time: 600,
    elapsed: 0,
    completed: false,
    active: false,
    current: true,
  },
  {
    _id: 4,
    name: "See Solution",
    time: 600,
    elapsed: 0,
    completed: false,
    active: false,
    current: true,
  },
];

```

For storing the time, I'll use seconds as the unit. I don't think further precision will be need.&#x20;

I don't know how to work with local storage yet, So I'll follow some tutorial.&#x20;
