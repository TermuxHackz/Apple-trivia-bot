# Apple Trivia Bot

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Initial Server Setup](#initial-server-setup)
4. [Bot Configuration](#bot-configuration)
5. [Role Permissions](#role-permissions)
6. [Command Overview](#command-overview)
7. [Trivia System](#trivia-system)
8. [Leaderboard System](#leaderboard-system)
9. [Subscription System](#subscription-system)
10. [Customization](#customization)
11. [Troubleshooting](#troubleshooting)
12. [Advanced Features](#advanced-features)
13. [Server Authorization](#server-authorization)
14. [Achievements System](#achievements-system)
15. [Hint System](#hint-system)

## Introduction

Apple Trivia Bot is a Discord bot designed to engage server members with exciting trivia questions about Apple Inc., its products, services, and history. It offers an interactive way to learn about Apple while competing with other server members.

## Features

- Automated trivia questions at customizable intervals
- Multiple-choice questions with interactive buttons
- Customizable trivia question timeout
- Leaderboard system to track user scores
- Customizable trivia and leaderboard reset intervals
- Subscription system for trivia notifications
- Admin commands for easy bot management
- User-friendly commands for participants

## Role Permissions

The Apple Trivia Bot uses a role-based permission system for administrative commands. The following roles have access to admin commands:

- Senior Mod
- Manager
- Admin
- Server Owner
- Moderators

## Initial Server Setup

After inviting the bot to your server, follow these steps:

1. **Set the Trivia Channel:**
Use the command `/set_channel #your-trivia-channel` to designate where trivia questions will be posted.

2. **Create Subscriber Role:**
Run `/create_subscriber_role` to create a role for users who want to receive trivia notifications.

3. **Set Trivia Interval:**
Use `/set_interval` to determine how often trivia questions are posted.

4. **Set Leaderboard Reset Interval:**
Configure how often the leaderboard is sent and then resets with `/set_leaderboard_interval`.

5. **Set Trivia Timeout:**
Use `/set_trivia_timeout` to set the duration for which each trivia question remains active.

## Bot Configuration
- The Apple Trivia Bot can be configured using the `/configure` command

  
### Trivia Channel
- Command: `/set_channel #channel`
- Description: Sets the channel where trivia questions will be posted.
- Usage: `/set_channel #trivia-fun`

### Subscriber Role
- Command: `/create_subscriber_role`
- Description: Creates a "Trivia Subscriber" role for notification opt-ins.
- Note: This role is crucial for the subscription system to work.

### Trivia Interval
- Command: `/set_interval [days] [minutes]`
- Description: Sets how frequently trivia questions are posted.
- Usage: `/set_interval days:0 minutes:30` (for every 30 minutes)

### Leaderboard Reset
- Command: `/set_leaderboard_interval [days] [hours] [minutes]`
- Description: Configures how often the leaderboard get sent and resets.
- Usage: `/set_leaderboard_interval days:7 hours:0 minutes:0` (weekly sends reset)

### Trivia Timeout
- Command: `/set_trivia_timeout [seconds]`
- Description: Sets the duration for which each trivia question remains active.
- Usage: `/set_trivia_timeout 45` (for 45 seconds)
- Note: The timeout can be set between 20 seconds and 5 minutes (300 seconds).

## Command Overview

### Admin Commands
(Note: These commands are only accessible to users with Senior Mod, Manager, Admin, Moderators roles, or the Server Owner)

- `/set_channel [channel]`: Set the announcement channel for trivia questions
- `/get_config`: Get the current configuration (announcement channel)
- `/delete_channel`: Delete the current announcement channel
- `/set_interval [days] [minutes]`: Set the interval between trivia questions
- `/set_leaderboard_interval [days] [hours] [minutes]`: Set the interval for automatic leaderboard to be sent (default 4 weeks)
- `/reset_leaderboard`: Reset the leaderboard
- `/create_subscriber_role`: Create a role for trivia subscribers
- `/set_trivia_timeout [seconds]`: Set the timeout for trivia questions (20 seconds to 5 minutes)
- `/check_authorization`: Check if your Server is authorised to use the Bot.

### User Commands
- `/toggle_trivia_sub`: Subscribe or unsubscribe from trivia notifications
- `/help`: Show the help message with available commands
- `/about`: Show information about the bot
- `/ping`: Check if the bot is running
- `/uptime`: Check how long the bot has been running
- `/profile [user]`: View your own or another user's trivia profile
- `/achievements [user]`: View your own or another user's achievements
- `/fetch_leaderboard`: Fetch the current leaderboard

## Profile System

The Apple Trivia Bot now includes a profile system that allows users to view their trivia statistics and those of other users.

### Viewing Profiles

- Command: `/profile [user]`
- Description: Displays the trivia profile for yourself or another user.
- Usage: 
  - `/profile` (to view your own profile)
  - `/profile @username` (to view another user's profile)

### Profile Information

The profile includes the following information:

- Total Score: The user's cumulative score from all trivia questions.
- Correct Answers: The total number of questions the user has answered correctly.
- Questions Answered: The total number of questions the user has attempted.
- Accuracy: The percentage of correct answers out of total questions answered.
- Current Streak: The number of consecutive days the user has answered at least one question correctly.
- Best Streak: The user's longest streak of consecutive days with correct answers.
- Hints Used: The number of hints the user has used in the current leaderboard period.
- Hints Remaining: The number of hints the user can still use before the next reset.

### Checking Other Users' Streaks

You can easily check another user's streak and other stats by mentioning them in the profile command:

1. Use the command `/profile @username`
2. The bot will display the profile for the mentioned user, including their current streak and best streak.

This feature allows for friendly competition and encourages regular participation in the trivia games.

## Trivia System
- Questions can be either text-based or image-based
- Each question is multiple-choice with four options
- Users have a customizable amount of time to answer using interactive buttons (default 30 seconds, can be set between 20 seconds and 5 minutes)
- Correct answers award points based on the question type and whether a hint was used
- Questions are automatically posted at the set interval in the designated channel
- Users can request hints, but this reduces the points awarded for a correct answer

### Point System
- Text-based questions:
  - 4 points for a correct answer without using a hint
  - 2 points for a correct answer after using a hint
- Image-based questions:
  - 3 points for a correct answer without using a hint
  - 2 points for a correct answer after using a hint
- Incorrect answers always result in 0 points

### Image-Based Questions
- In addition to text-based questions, the bot supports image-based trivia
- Image questions typically ask users to identify an Apple product shown in the image
- Images are generated using AI technology, ensuring a wide variety of unique visual questions
- The image is displayed within the trivia question embed for easy viewing
- Users answer image questions in the same way as text questions, using the multiple-choice buttons
- This feature adds a visual element to the trivia game, making it more engaging and diverse

The addition of image-based questions enhances the trivia experience by:
- Providing visual variety to the question format
- Testing users' ability to recognize Apple products visually
- Increasing engagement through interactive visual content
- Offering a more diverse and challenging trivia experience

Both text-based and image-based questions contribute to users' scores and achievements, with image questions being slightly less valuable to balance their potentially easier nature.

## Hint System

The Apple Trivia Bot includes a hint system to help users with challenging questions:

### Hint Usage

- Users can request a hint for each trivia question by clicking the "Hint" button.
- Hints provide partial information about the correct answer, such as revealing some letters or words.
- Each user has a limited number of hints they can use per leaderboard reset interval (default is 2).
- The hint limit resets along with the leaderboard at the interval set by `/set_leaderboard_interval`.

### Hint Costs

- Using a hint reduces the points awarded for a correct answer:
  - For text-based questions: from 4 to 2 points
  - For image-based questions: from 3 to 2 points
- Incorrect answers after using a hint still result in 0 points.

### Hint Reset

- Hint usage is reset for all users in a server when the leaderboard resets.
- This ensures that all users have an equal opportunity to use hints in each leaderboard period.

These updates reflect the new point system, including the differentiation between text-based and image-based questions, and how hints affect scoring. The hint system explanation has also been adjusted to account for the different point values for each question type.
## Leaderboard System

- Tracks user scores across all trivia questions
- Can be viewed using the `/fetch_leaderboard` command
- Sends and Resets automatically at the interval set by `/set_leaderboard_interval`
- Can be manually reset by admins using `/reset_leaderboard`

## Subscription System

- Users can opt-in to receive notifications for new trivia questions
- Utilizes the "Trivia Subscriber" role created by `/create_subscriber_role`
- Users toggle their subscription status with `/toggle_trivia_sub`
- Subscribers are mentioned when new trivia questions are posted

## Customization

Admins can customize various aspects of the bot:
- Trivia question frequency
- Leaderboard reset interval
- Announcement channel for trivia questions
- Trivia question timeout duration

## Achievements System

The Apple Trivia Bot now includes an achievements system to reward users for their participation and performance in trivia games.

### Available Achievements

- **Apple Seed**: Answer your first question correctly
- **Apple Sapling**: Answer 10 questions correctly
- **Apple Tree**: Answer 50 questions correctly
- **iMaster**: Answer 100 questions correctly
- **Hat Trick**: Achieve a 3-day streak
- **Weekly Wonder**: Achieve a 7-day streak
- **Monthly Master**: Achieve a 30-day streak

### Viewing Achievements

- Command: `/achievements [user]`
- Description: Displays the achievements for yourself or another user.
- Usage: 
  - `/achievements` (to view your own achievements)
  - `/achievements @username` (to view another user's achievements)

The achievements view shows both unlocked (✅) and locked (🔒) achievements, allowing users to see their progress and what they can strive for next.

### Unlocking Achievements

Achievements are automatically unlocked as you participate in trivia games and meet the required criteria. When you unlock a new achievement, you'll receive a notification after answering a question correctly.

This feature adds an extra layer of engagement to the trivia game, encouraging users to participate regularly and improve their performance to unlock all achievements.


## Advanced Features

### Natural Language Processing (NLP)

The Apple Trivia Bot utilizes advanced NLP techniques to enhance its functionality:

- **SpaCy Integration**: The bot uses the SpaCy library for sophisticated text processing. This allows for more accurate interpretation of user inputs and generation of high-quality trivia questions.

- **Sentence Transformers**: Employs the 'all-MiniLM-L6-v2' model for generating sentence embeddings, enabling advanced semantic analysis of trivia questions and user responses.

### Similarity Checks

To ensure the uniqueness and quality of trivia questions, the bot implements several similarity checking mechanisms:

- **Question Deduplication**: Before adding a new question to the database, the bot performs similarity checks against existing questions to prevent duplicates or very similar questions from being added.

- **Semantic Similarity**: Uses sentence embeddings to compute semantic similarity between questions, allowing for detection of questions that are phrased differently but have the same meaning.

- **Customizable Threshold**: Administrators can adjust the similarity threshold to fine-tune the balance between question uniqueness and variety.

### Adaptive Difficulty

The bot includes an adaptive difficulty system that adjusts the complexity of questions based on user performance:

- **User Performance Tracking**: Monitors individual user scores and overall server performance.

- **Dynamic Question Selection**: Selects questions from different difficulty tiers based on the current performance metrics.

## Server Authorization

The Apple Trivia Bot is a private bot designed for exclusive use in specific Discord servers. Currently, only the following servers are authorized to use this bot:

1. [The Apple Den Server](https://discord.gg/appleden)
2. [The Test Server](https://discord.gg/pf66AXK8cW)

Read privacy policy [here](https://bit.ly/3AXpgCj)

### Important Notes:
- The bot will automatically leave any server it is added to that is not on the authorized list.
- Attempts to use the bot's commands in unauthorized servers will result in an error message.

### For Server Owners:
If you believe your server would benefit from the Apple Trivia Bot and would like to request authorization, please contact the bot developer directly (discord: techcodes27). Please note that authorizations are granted on a case-by-case basis, and the bot is intended to remain exclusive to a limited number of servers.

## Privacy and Data Handling

As a private bot, the Apple Trivia Bot adheres to strict privacy guidelines:
- User data is only collected and stored for the authorized servers.
- Leaderboard information and user scores are server-specific and not shared between authorized servers.
- The bot does not collect or store any personal information beyond what is necessary for its trivia and leaderboard functionalities.

## Troubleshooting

If you encounter issues:
1. Ensure the bot has necessary permissions in your server
2. Confirm that the "Trivia Subscriber" role exists and is properly set up
3. Ensure that all required roles (Senior Mod, Manager, Admin, Moderators) are set up and exist in your server
4. Verify that users trying to use admin commands have the appropriate roles
5. Check that the trivia timeout is set to a valid duration (between 20 seconds and 5 minutes only in Seconds)

For persistent issues, please contact the bot developer with detailed information about the problem.
