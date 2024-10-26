---

title: "Final submission report"  
image: ../assets/images/logo.png  
categories:
  - Weekly Log  
tags:
  - GitHub Pages  

---

# Goals of the project

The goal of this GSoC project was to enhance BT Studio, a web-based IDE for robotic applications that uses behavior trees.

When I joined the project, BT Studio could only handle basic behavior trees, which were limited to control blocks (e.g., sequences, fallbacks) and actions written in Python.

This setup, however, didn’t fully leverage the flexibility and modularity of behavior trees, particularly through subtree composition, dividing logic into smaller subtrees that can be reused across different applications. This simple concept changes radically how to create applications with BT Studio. 

My objective was to create the tools necessary to enable subtree use in BT Studio. This involved, among other things, frontend updates to support navigation between various blocks, changes to the graph editor, and backend adaptations to handle this logic effectively.

After that, the goal was to create a basic library of behaviors using these tools, that the users could directly reuse in their applications. These behaviors could include things like obstacle avoidance or person tracking. 

# My contribution

I successfully achieved all the proposed goals, implementing the composition tools across both the backend and frontend. Additionally, I developed four reusable subtrees for the library, along with the necessary modifications to make importing them straightforward.

In the process, I reimplemented a lot of components using TypeScript for and refactored their logic to better manage the state and adhere to important React concepts like component purity and state inmutability.

In addition, I also expanded the universe functionality (in BT Studios, universes are different simulation environments) to allow for user-made custom ones. Now the users can upload a universe in a zip file. 

Throughout my GSoC contribution, I actively participated in community discussions and took a proactive role in reviewing the work of other contributors.

# Current state

![multilevel_composition]({{ site.baseurl }}/assets/images/week11/multilevel_composition.gif)

All my contributions have been merged upstream, and multilevel composition—allowing subtrees to contain other subtrees at any depth—is now fully functional. This feature works seamlessly with both offline apps (executed directly on ROS 2 Humble) and in the dockerized execution environment of JdeRobot. 

You can see an example of how the composition tools and the library work in the video I created showcasing my contributions. 

# Future work

* Cyclic subtree check
* Better library UI
* Expanding the library
* Better UI for moving between different subtrees. 

# Merged pull requests

* [Enforcing style with CI/CD](https://github.com/JdeRobot/bt-studio/pull/157)
* [Support for custom universes](https://github.com/JdeRobot/bt-studio/pull/144)
* [API calls standardization](https://github.com/JdeRobot/bt-studio/pull/174)
* [Component refactorization](https://github.com/JdeRobot/bt-studio/pull/190)
* [Subtree composition with depth 1](https://github.com/JdeRobot/bt-studio/pull/194)
* [Subtree composition with depth N](https://github.com/JdeRobot/bt-studio/pull/204)
* [Basic library of reusable subtrees](https://github.com/JdeRobot/bt-studio/pull/209)

# Challenges and lessons