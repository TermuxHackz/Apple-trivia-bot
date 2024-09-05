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
- `/fetch_leaderboard`: Fetch the current leaderboard
- `/create_subscriber_role`: Create a role for trivia subscribers
- `/set_trivia_timeout [seconds]`: Set the timeout for trivia questions (20 seconds to 5 minutes)

### User Commands
- `/toggle_trivia_sub`: Subscribe or unsubscribe from trivia notifications
- `/help`: Show the help message with available commands
- `/about`: Show information about the bot
- `/ping`: Check if the bot is running
- `/uptime`: Check how long the bot has been running

## Trivia System

- Questions are generated using the Perplexity API
- Each question is multiple-choice with four options
- Users have a customizable amount of time to answer using interactive buttons (default 30 seconds, can be set between 20 seconds and 5 minutes)
- Correct answers award 4 points to the user's score
- Questions are automatically posted at the set interval in the designated channel

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

## Troubleshooting

If you encounter issues:
1. Ensure the bot has necessary permissions in your server
2. Confirm that the "Trivia Subscriber" role exists and is properly set up
3. Ensure that all required roles (Senior Mod, Manager, Admin, Moderators) are set up and exist in your server
4. Verify that users trying to use admin commands have the appropriate roles
5. Check that the trivia timeout is set to a valid duration (between 20 seconds and 5 minutes only in Seconds)

For persistent issues, please contact the bot developer with detailed information about the problem.