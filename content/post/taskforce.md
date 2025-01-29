---
title: TaskForce
subtitle: Be more productive, or get roasted by AI (UofTHacks)
date: 2025-01-18
tags: ["full-stack", "hackathon", "genAI"]
---

Ever gone on LinkedIn and all you saw was “I’m happy to share that I will be working at `{Google, Microsoft, Meta, Tesla, etc}` this summer”. You probably thought to yourself, “Wow, I really have to start working harder.” That feeling – the urge to level up your own productivity – is a powerful motivator. We recognized this common experience and decided to harness it.

Chi, Nicholas, Dylan, and I built TaskForce, a desktop productivity app where you can **create and join study sessions with your friends to roast each other and brag about locking in with GenAI and system-tracking informed analytics in real time!!**

{{< columns >}}
{{< figure link="/img/taskforce/home.png" alt="Homepage" >}}
{{< column >}}
{{< figure link="/img/taskforce/design.png" alt="System Design">}}
{{< endcolumns >}}

<!--more-->

## Features

- **Device Usage Tracking**: Monitor your device activity in real-time, including active apps and browser tabs, with intelligent classification of activities as productive or non-productive. 📊

- **AI Roasting & Encouragement**: Receive AI-generated roasting messages (including funny Steven He and Uncle Roger voices) and humorous encouragements to stay focused and motivated. 🤖

> We for sure know how to keep the GenZ engaged!! 🤣

- **Focus Group Sessions**: Host or join focus sessions with friends. When you perform well in a session, we send AI generated bragging messages to everyone else to boost your ego. 🚀

- **Mock LinkedIn Posts**: Share your productivity achievements on a mock LinkedIn feed to motivate yourself and your friends. Get ready to flex on your peers! 🏆

## Tech Stack

- **Frontend**: HTML, JavaScript, CSS, Electron App
- **Backend**: Flask, Gemini API, Socket.io, Redis, Firebase
