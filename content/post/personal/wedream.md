---
title: WeDream
subtitle: Duolingo for Sleep
date: 2024-06-01
tags: ["personal-projects", "ios"]
disable_header: false
skills: ["Swift", "XCode", "Firebase", "Express"]
---

Sleep deprivation is a widespread issue, expected to worsen as distractions increase. Despite understanding sleep's benefits, many find it challenging to maintain a healthy night routine. This is especially prominant for students who later face difficulties in focusing and retaining information.

{{< gallery caption-effect="fade" >}}
{{< figure link="/img/wedream/demo1.png" caption="Real In-app footages">}}
{{< figure link="/img/wedream/logo.png" caption="WeDream Logo">}}
{{< figure link="/img/wedream/demo2.png" caption="Not Figma prototypes">}}
{{< /gallery >}}

Inspired by the engaging features of Duolingo, WeDream motivates users to stay committed to improving their sleep habits. We are dedicated to empowering individuals who actively seek to improve their daily lives and become the best versions of themselves.

> This is a course project for ICS4U, a grade 12 computer science course in Ontario, Canada. Feel free to fork this project to create your own custom sleep improvement app!

## Features

1. **Streak tracking:** Keep up with your sleep goals by maintaining a streak.

2. **Compete:** Earn rewards and compete with other users in a leaderboard.

3. **Gamification:** Complete daily challenges that encourage healthy sleep habits.

4. **Social Networking:** Connect with friends and learn from their tips and tricks.

5. **Real-Time Sleep Data:** Access accurate sleep data analytics from health wearables like Apple Watch.

## Technologies

| Tool                | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Figma               | Prototyping and design tool for designing app interfaces and user experiences|
| XCode               | Integrated development environment for macOS, used for developing and testing iOS applications|
| Swift               | Programming language for iOS and macOS development, used for writing the app's code|
| SwiftUI             | Framework for building user interfaces on Apple platforms, used for creating the app's UI|
| iOS Kit | Tools like HealthKit API for accessing health and fitness data, used for integrating health data into the app|
| Firebase            | Platform for user authentication and database management|
| Express.js          | Web application framework for Node.js, used for building the backend server|

SwiftUI is great because it simplifies the process of building user interfaces and state management. For example, here is the raw structure for our leaderboard view (largely simplified):

```swift
var body: some View {
    NavigationView {
        List {
            ForEach(viewModel.players.indices, id: \.self) { index in
                let player = viewModel.players[index]
                let rank = index + 1 // use index to show players' rank

                NavigationLink(destination: LazyProfileView(userId: player.id)) {
                    HStack {
                        // ... show player's profile picture, name, and streak
                    }
                    .frame(maxWidth: .infinity, minHeight: 60)
                    .background(
                        // ... show background color based on player's rank
                    )
                    .padding(.horizontal)
                    .padding(.vertical, 5)
                }
            }
        }
        .listStyle(PlainListStyle())
        .navigationTitle("Leaderboard")
    }
    .onAppear {
        viewModel.fetchPlayers() // Fetch leaderboard data when view appears
    }
}
```

SwiftUI allows developers to create complex and dynamic views with visually appealing styling conveniently. It enables a focus on **"how the app is supposed to behave"** rather than _"how to achieve the functionality."_ The concise and readable code makes it an excellent choice for building the WeDream app. Transitioning from a C++ background, working with Swift has been a refreshing and enjoyable experience.

Looking forward to building more projects with SwiftUI and Swift in the future!

{{< button url="https://drive.google.com/file/d/1t98hih2oPN2OMlbaCXA8FJT0SDIl-aSB/view" >}}Learn more about WeDream here!{{< /button >}}
