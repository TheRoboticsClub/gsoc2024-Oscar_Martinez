---

title: "Final submission report"  
image: ../assets/images/logo.png  
categories:
  - Weekly Log  
tags:
  - GitHub Pages  

---

# Goals of the project

The goal of this GSoC project was to enhance BT Studio, a web-based IDE for robotic applications that uses behavior trees, by adding composition capabilities.

When I joined, BT Studio could only handle basic behavior trees, limited to control blocks (e.g., sequences, fallbacks) and actions written in Python.

However, this setup didn’t fully leverage the flexibility and modularity of the behavior tree paradigm. Through subtree composition, behavior trees allow the application logic to be divided into smaller, reusable subtrees that can be applied across various use cases. This simple concept fundamentally changes how applications can be created within BT Studio.

My objective was to develop the necessary tools to enable subtree use in BT Studio. This involved frontend updates for navigating between blocks, changes to the graph editor, and adaptations to the backend API to handle this logic effectively.

After that, the goal was to build a basic library of behaviors using these tools that users could directly incorporate into their applications. These behaviors could include functionalities like obstacle avoidance or person tracking.

# My contribution

I successfully achieved all the proposed goals, implementing the composition tools across both the backend and frontend. Additionally, I developed four reusable subtrees for the library, along with the necessary modifications to make importing them straightforward.

In the process, I reimplemented a lot of components using TypeScript for and refactored their logic to better manage the state and adhere to important React concepts like component purity and state inmutability.

In addition, I also expanded the universe functionality (in BT Studios, universes are different simulation environments) to allow for user-made custom ones. Now the users can upload a universe in a zip file. 

Throughout my GSoC contribution, I actively participated in community discussions and took a proactive role in reviewing the work of other contributors.

# Current state

![multilevel_composition]({{ site.baseurl }}/assets/images/week11/multilevel_composition.gif)

All my contributions have been merged upstream, and multilevel composition (allowing subtrees to contain other subtrees at any depth) is now fully functional. This feature works seamlessly with both offline apps (executed directly on ROS 2 Humble) and in the [dockerized execution environment of JdeRobot](https://hub.docker.com/r/jderobot/robotics-academy). 

You can see an example of how the composition tools and the library work in this video I created showcasing my contributions. 

# Future work

During my contribution, I've become aware of the different limitations and possible work to be done for future contributions: 

1. **Checking subtree loops**: implement a system to detect and prevent recursive loops at any level within the behavior tree (e.g., X → Y → Z → X). This will safeguard against infinite loops, ensuring that subtrees remain functional. Currently, the application would hang indefinitely trying to substitute the trees XML. 

2. **Improving the library UI**: redesign the library interface for easier navigation and discovery of behaviors, including better categorization, search, and filtering. In the current initial implementation, the user has to explicitly type the name of the component to import. 

3. **Expanding the subtree library**: add more pre-built behaviors, covering advanced applications like navigation and interaction, to provide users with a broader toolkit for building complex applications.

4. **Enhancing navigation within subtrees**: create a smoother interface for moving between subtrees, possibly using a breadcrumb trail or hierarchy view. This will help users easily manage complex behavior tree structures. 

I'm planning to continue working with JdeRobot in the coming months to tackle these issues and keep improving BT Studio!

# Merged pull requests

* [Enforcing style with CI/CD](https://github.com/JdeRobot/bt-studio/pull/157)
* [Support for custom universes](https://github.com/JdeRobot/bt-studio/pull/144)
* [API calls standardization](https://github.com/JdeRobot/bt-studio/pull/174)
* [Component refactorization](https://github.com/JdeRobot/bt-studio/pull/190)
* [Subtree composition with depth 1](https://github.com/JdeRobot/bt-studio/pull/194)
* [Subtree composition with depth N](https://github.com/JdeRobot/bt-studio/pull/204)
* [Basic library of reusable subtrees](https://github.com/JdeRobot/bt-studio/pull/209)

# Challenges and lessons

The main challenges I encountered during my GSoC project were primarily technical. I had to dive deeply into advanced React concepts, including memoization and complex state management, which pushed me to significantly expand my skills in frontend development. Additionally, I developed a much stronger understanding of RESTful APIs, learning to design and implement them more effectively.

One of the highlights of this experience was collaborating with the other contributors. I really enjoyed discussing different approaches and solutions, which not only broadened my perspective but also improved my ability to work as part of a team. This project has been both challenging and rewarding, providing valuable experience in both technical and collaborative skills.

Thanks for following along! Here’s to many more lines of code, lessons learned, and projects shared. Until next time—happy coding! 😊🚀