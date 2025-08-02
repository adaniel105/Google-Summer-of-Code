# GSoC Community Hub 2025 - Work Summary
**Mentee:** Daniel Akinola  

**Mentor(s):** [Anjaneya Gupta](https://github.com/anjy7), [Dhruv Jain](https://github.com/dhruvjain99)

**Organization:** Rocket.Chat  

**Project Link:** https://summerofcode.withgoogle.com/programs/2025/projects/F5Xyt695

**Repository:** https://github.com/RocketChat/GSoC-Community-Hub  

<div align="center">
<a href="https://summerofcode.withgoogle.com/programs/2025/projects/F5Xyt695"><img src="https://i.imgur.com/pgkUceb.png" width="650" alt="google-summer-of-code"></a>
<br>
</div>

## 📋 Overview

The Google Summer of Code Community Hub project for Rocket.Chat is centered around developing a full-stack web application designed to streamline collaboration for open-source communities. It is intended to be an easy to use, ready-for-customization, community engagement and management system specially designed for Google Summer of Code communities.

Components are specified in an `.agml` component layout file with an HTML-tag like domain specific language, and transformed into full-fledged, functional components by a robust compilation system which utilizes the TypeScript Compiler API at its core. This year's work iterates on the previous years, moving the entire framework over to Svelte5 and Bun, and simplifying the build process from the previous iterations.

The project aims to provide organizations with a turnkey solution for managing their GSoC communities, featuring dynamic leaderboards, embedded chat functionality, video conferencing capabilities, and customizable event management tools. The framework's component-based architecture allows organizations to easily customize their community hubs without extensive development knowledge.



## 🎯 Objective
The primary aim of this project will be the refactoring of a domain specific language compiler to produce Svelte components rather than React Components, in order to enable the translation of components specified using minimal syntax to robust, secure and functional web applications at scale. Multiple components will be implemented using the new svelte framework , such as a video conferencing meet-your-mentor component, and a gsoc Leaderboard component which would allow for the gamification of contributions to the Rocket.Chat community. Finally, all components will be adapted to fully meet the pre-scaled “serverless” vision for the application, so components can be specified can be specified using terse syntax and transformed into full fledged applications at build time. All of this will culminate in the implementation of a functional Community Hub to be used for future summers.



## ✅ What I Accomplished

### 1. DSL Compilation System Migration
-  Porting of the application's core compilation system from NextJS (React) & Node to Svelte5 and Bun.
-  Modified parsing of .agml files to produce Svelte5 functional components rather than React.

### 2. Component Implementation Using New Framework
- Implementated the following components using the new and improved framework:
  - GSOC leaderboard (for gamification of contributions to the respective organization)
  - Embeddedchat (seamless Rocket.Chat integration for community communication)
  - A video-conferencing component (video calling functionality for community meetings)
  - Completion of the EventPoster component 
- Implemented build scripts which would run at intervals for components that require updates

### 3. Build Pipeline Modification
- Modified the directory structure to seperate the framework from code/components generated.
- Refactored the compiler to accomodate said changes in build paths


## 🕸 Challenges Faced 

### 1. Handling Updates for Real Time components
Figuring out how components with real-time updates would fit in our static and lightweight application was an initial challenge, 
but a workaround using build scripts which would run at periodic intervals was implemented, and resolved this problem

### 2. Cross-Domain Authentication
Implementing single sign-on authentication across different domains proved technically challenging and complex. Redefined requirements to simplify the authentication architecture. The new approach requires the authentication provider and application to be deployed on the same domain, eliminating cross-domain complexities and effectively sidestepping the problem.

### 3. Framework Migration Complexity
Migrating from React to Svelte5 while maintaining existing functionality and component compatibility.

## ⛓️ Relevant Merge Requests
- [#47 - Layer back DSL from 2024](https://github.com/RocketChat/GSoC-Community-Hub/pull/47)
- [#61 - Fetch data for the Statscounter component](https://github.com/RocketChat/GSoC-Community-Hub/pull/61)
- [#67 - Addition of GSOC leaderboard](https://github.com/RocketChat/GSoC-Community-Hub/pull/67)
- [#76 - Fixing Directory Structure](https://github.com/RocketChat/GSoC-Community-Hub/pull/76)
- [#79 - Addition of video conferencing component](https://github.com/RocketChat/GSoC-Community-Hub/pull/79)
- [#81 - Implementation of the Embeddedchat component](https://github.com/RocketChat/GSoC-Community-Hub/pull/81)
- [#82 - Data fetching for the Eventposter](https://github.com/RocketChat/GSoC-Community-Hub/pull/82)

## 📋 Learning Experience

GSoC'25 with Rocket.Chat has been an incredibly rewarding experience. Before starting, I was relatively new to Svelte and had never worked with DSL compilation systems. Thanks to GSoC, I've gained confidence and skills. Although I still have a long way to go, working on the Community Hub has inspired me to explore further and contribute more to open-source projects.
Interacting with the Rocket.Chat community and receiving advice from my mentors has been invaluable. I feel like I've made some great connections along the way, which has made the experience even more enjoyable.
Here are some key lessons I've learned during my time with Rocket.Chat:

- TypeScript Compiler API: I had never worked with the typescript compiler api prior to this project, and this proved to be one of the initial hurdles to my first ever commit to Rocket.Chat, but over time, researching AST concepts, typescript, and just tinkering with the project, I have explored a good amount of its functionality and applicability, and would be comfortable using it in future projects.
- Working with Open source tooling: This project significantly enhanced my knowledge and ability to utilize tooling from within the wider open source ecosystem. Open source solutions were used extensively in the implementation of each of my components i.e Jitsi, Keycloak e.t.c and this project helped enhance my ability to understanding and integrated these respective tools.

## ⚙️ What's Left to Do?

While significant progress was made, several areas remain for future development:

### 1. Package Installation Functionality
- **Requirement**: Implement automated package installation based on selected components
- **Current State**: All dependencies installed on base project
- **Next Steps**:  Install dependencies only as needed by the respective specified components

### 2. User Authentication Implementation
- **Requirement**: Complete user authentication using open source authentication providers
- **Current State**: Architecture and foundation completed
- **Next Steps**:Implement OAuth2/OIDC integration with popular providers (Auth0, Keycloak, etc.)

### 3. Super Profile and Login Persistence
  Develop comprehensive user profile management with session persistence

### 5. Testing and Deployment
- Implememtation of a CI/CD pipeline for automated testing and deployment

## Conclusion

I'm deeply grateful to the Rocket.Chat community and development team for giving me the chance to contribute to this project. This experience has not only improved my programming skills but also made me appreciate the collaborative nature of open-source development.

A big thank you to my mentors, Anjaneya Gupta and Dhruv Jain, for their ongoing support and guidance throughout the GSoC project. Their timely responses and insightful advice made the process smoother and helped me overcome many challenges.
I'm excited to keep contributing to the Community Hub project and look forward to future opportunities to grow and learn with Rocket.Chat.

Working with the Rocket.Chat team and my mentors has been an incredibly rewarding experience. Their guidance, code reviews, and technical discussions significantly contributed to both the project's success and my professional development.

The Community Hub project is now well-positioned for continued development and adoption by GSoC organizations worldwide, providing them with powerful tools to manage and engage their communities effectively.


**Project Repository**: https://github.com/RocketChat/GSoC-Community-Hub . Check the project out and give it a star ⭐!
