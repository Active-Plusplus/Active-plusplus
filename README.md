# Active-plusplus
Original App Design Project - README Template
===

# Active++

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
Active++ is a fitness app that seeks to help people getting into weight lifting in a gym setting. It allows users to track their progress and apply proper principles for training to help them acheive their ultimate fitness goals. 

### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** Lifestyle/Productivity
- **Mobile:** The primary focus of this app will be on mobile as it will allow for the most functionality. However, if possible an expansion to a web application would also be great. 
- **Story:** Analyzes users music choices, and connects them to other users with similar choices. 
- **Market:** Any individual could choose to use this app. Whether the user is a beginner or an experienced lifter, all users can find valuable information for their fitness goals. 
- **Habit:** This app can be utilized as frequently as the user goes to workout. It can be used to track in between sets/reps and track progress overtime. 
- **Scope:** First we will start with the app focusing on providing general information on exercises and targetted muscle groups. Then the app could evolve into users creating public plans that other users can follow. Finally, if time permits we would love to make the app a shareable platform. 

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* ---- User Story ---- #1 - Create A Custom Fitness Program - 
As a user of the program, I want to be able to create a custom fitness plan.
a) Description: A program can be made which allows a user to add specific exercises, sets, and reps into a customized program. Ability to allow users to add a custom name.
b) Assumptions: Assumed that tabbed view controller with create option has already been implemented. We should assume an API has read and created different exercise objects, which can then be mapped to different scrolling option tabs. This custom program will then be stored in a custom program object and then appended onto a vector/array holding which holds different programs. Programs created will persist through changes.
c) Tasks: Create objects from each exercise through the API, and make them options in the scrollable options list. Include ability to track sets and reps for each exercise, stored in a program object, which will have private members of an array/vector of exercises. Programs made can then be appended into an array/vector which will be persisted and can be accessed in the future by clicking “My Programs” from the home-page.
d) Estimation: -
e) Priority: -
f) Done: The user will be able to create a custom program, which includes exercises, sets and reps. This program will be able to be persisted over changes.

* ---- User Story ---- #2 - Record Workouts  - 
As a user of the program, I want to be able to record my workouts and keep track of each day I do them.
a) Description: Workouts can be added into different days, with 7 preset days (Monday-Sunday) being blank at first. A user can add a custom program they have created into each day. These will be persisted over time.
b) Assumptions: Assumed that tabbed view controller with record option has already been implemented. We should assume an API has read and created different exercise objects, and a program has been created using those objects, stored in a vector. Assume custom program implementation complete, as those are needed to add to record for each day. Workouts created will persist through changes.
c) Tasks: Create slots for Monday-Sunday, with a rest option as the first available. Ability to add custom programs into each days’ slot. Persist changes.Plus button at top will lead to create a program page.
d) Estimation: -
e) Priority: -
f) Done: The user will be able to record workouts using custom programs they have made.

* ---- User Story ---- #3  - API Parsing + Exercise Page - 
As a user of the program, I want to be able to view different exercises through an API.
a) Description: Users can view different exercises in the exercises tab, which are sorted by category of muscle they are for. Clicking on an exercise will open a specific window for that exercise, and that exercises GIF and a brief description will show. 
b) Assumptions: Tabbed view controller is made.
c) Tasks: Parsing the API file and creating a new Exercise object for each item in the API, and then pushing those into a vector, sorted by category. Then navigation screen instances must be made in order to readily go to each area of this section of the app. Exercises parsed must be pushed into a scrolling view controller which shows exercises by category with headings for each.
d) Estimation: -
e) Priority: -
f) Done: The user will be able to view an exercises page through parsing an API.

* ---- User Story ---- #4  - Tabbed View Controller and Flow Creation  - 
As a user of the program, I want to be able to navigate the app using different views and tabbed bars.
a) Description: Users can navigate throughout different app aspects.
b) Assumptions: App icons are available.
c) Tasks: Create tabbed view controller and different screens for program flow. (See chart for specific layouts)
d) Estimation: -
e) Priority: -
f) Done: The user will be able to navigate the app with ease.

* ---- User Story ---- #5  - HomePage Creation  - 
As a user of the program, I want to be able to view my workouts and information on the homepage.
a) Description: Users can view workouts and information on home page, as well as navigate to other tabs from here.
b) Assumptions: Custom workouts and record workouts are implemented.
c) Tasks: Create homepage to show custom and workouts, as well as make sure user arrives on this page on every app refresh.
d) Estimation: -
e) Priority: -
f) Done: The user will be able to view workouts and custom programs from homepage, as well as navigate to every other page from here.

**Optional Nice-to-have Stories**

* A user can add nutrition information and track food consumed.
* A user can follow workout plans from other people.

### 2. Screen Archetypes

* Screen 1 - Homepage
   * User Story 5
   * Homepage creation and navigation implementation to other parts of the app.
* Screen 2 - Add a Custom Program
   * User Story 1
   * Page to create a custom workout plan.

* Screen 3 - Record Workouts for Specific Days
   * User Story 2
   * Page to record specific workouts for days (Mon-Sun)

* Screen 4 - Exercise Listing Page
   * User Story 3
   * Page to view all exercises by category.

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Create Program 
* Exercises 
* Record Workout

Optional:
* Nutrition
* Follow a Program

**Flow Navigation** (Screen to Screen)

* (+) on Record Workout -> Prompts user to a screen where they can enter the exercises, sets, reps, and target goals
* (+) on Create a Program -> Jumps User to a new screen that allows them to enter exercises in a text field and sets/reps in a number field. 
* Selecting anywhere on an exercise cell -> Sends user to a more detailed description of the exercise

Optional:
* Selecting anywhere on another user's workout program -> Sends user to a screen with the full workout plan

## Wireframes
<img src="https://github.com/Active-Plusplus/Active-plusplus/blob/main/Wireframe.jpeg" width=600>


## Schema 
### Models
#### Post

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | objectId      | String   | unique id for the user's workout program |
   | author        | Pointer to User| Workout Program Author |
   | exerciseName | String   | Exercise name that user enters |
   | setAmount | Number   | Number of sets user wants |
   | repAmount | Number   | Number of reps user wants |
   | targetReps | Number   | Number of reps user is aiming for |
   | description       | String   | Description written  by the author about the program |
   | comments | String   | Additional Comments from the user in the workout plan |
   | createdAt     | DateTime | date when post is created (default field) |
   | updatedAt     | DateTime | date when post is last updated (default field) |

### Networking
   - Create a Workout Program Screen
      - (Create/POST) Query logged in user object
   - Exercise List Screen
      - (Read/GET) Query objects of exercises from API
   - Record a Workout 
      - (Create/POST) Query logged in user object
      - (Read/GET) Query all posts where user is author
         ```swift
         let query = PFQuery(className:"workoutProgram")
         query.whereKey("author", equalTo: currentUser)
         query.order(byDescending: "createdAt")
         query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
            if let error = error { 
               print(error.localizedDescription)
            } else if let posts = posts {
               print("Successfully retrieved \(posts.count) posts.")
           // TODO: Do something with posts...
            }
         }
         ```
      - (Create/POST) Create a new Workout Program 
   - Previous Workout Screen
      - (Delete) Delete Previous Workout
      - (Update/PUT) Update user's workout session
   - Follow Other Programs
      - (Create/POST) Query logged in user object
      - (Read/GET) Other user's workout programs

