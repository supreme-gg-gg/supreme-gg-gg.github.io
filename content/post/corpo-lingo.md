---
title: Corpo Lingo
subtitle: Get ready to buzzword your way to the top!
date: 2024-10-28
tags: ["javascript", "full-stack", "personal-projects"]
---

Ever felt lost in a sea of corporate jargon? Fear not! This project will turn you into a corporate lingo master, ready to impress in any boardroom.

{{< figure link="/img/corpo/home.png" caption="Homepage" >}}

<!--more-->

One night James and I were making jokes about corporate jargons and how they sound like a foreign language. We thought it would be fun to create a website that generates random corporate jargons and their meanings. We then went ahead to spend two days to build this website in vanilla HTML/Javascript with Bootstrap for styling and Express.js for the backend.

{{< figure link="/img/corpo/compete.png" caption="Compete with other real players" >}}

To allow for playres to play it against each other, we used websocket (socket.io) to allow for real-time updates of the scores. The game is simple: players are given a corporate jargon and they have to guess the correct meaning from a list of options. The faster they answer, the more points they get. **Socket.io made it easy to manage multiple connections and handle all requests in real-time.**

Furthermore, we utilitsed generative AI to create real life scenario of how these jargons are used in workspace conversations and emails, requiring the player to fill in the blanks with the correct choice. It was surprising how easy Gemini API was to use and how well it generated these scenarios.

```javascript
const genAI = new GoogleGenerativeAI(apiToken);
const model = genAI.getGenerativeModel({ model: "gemini-1.5-flash" });
const prompt = "...";
const result = await model.generateContent(prompt);
const generatedText = result.response.text();
const { scenario, correctAnswer, incorrectChoices } =
  parseOutput(generatedText);
res.json({ scenario, correctAnswer, incorrectChoices });
```

Our website is deployed on Render and you can try it out now!

{{< button url="https://corpo-lingo.onrender.com/" >}}Try our live website!{{< /button >}}
