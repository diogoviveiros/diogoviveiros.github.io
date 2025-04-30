---
title: "Advanced Paste Clipboard for Windows"
excerpt: "A C# coded productivity tool with a WPF (Windows Presentation Foundation) UI. Designed to reduce context-switching in repetitive communication tasks, like emails and scripting. Developed in collaboration with the Microsoft PowerToys team, who are committed to bringing power users a set of open source tool packages for productivity improvements."
collection: portfolio
---
[View Project on Github](https://github.com/diogoviveiros/EnhancedClipboardWPF). 

Advanced Paste is a productivity tool designed to reduce context-switching in repetitive communication tasks, like emails. Developed in collaboration with the Microsoft PowerToys team, who are committed to bringing power users a set of open source tool packages for productivity improvements.

For this project, I took on both Developer and Product Manager roles: I coded a working prototype, conducted market research, created user flows and a golden path, and developed presentations along with a comprehensive set of visual guidelines to help convince stakeholders of the project’s value.

# The Problem
From Executive Assistants managing schedules, to Support Engineers sending scoping questions or running PowerShell scripts, to Software Developers drafting detailed reports on their code, a large part of a modern professional’s day is dedicated to writing.

Often, this typing is repetitive: sending the same email templates, submitting standardized code reviews, or executing familiar scripts. To streamline these tasks, many users rely on programs like OneNote to store templates, which is a reasonable solution. However, switching to another application, locating the right template, copying it, and pasting it back into the original workspace introduces unnecessary friction. While each instance may only take a few seconds or minutes, over the course of a day, a week, a career, the lost time can add up significantly.

More importantly, this process introduces context switching. Moving away from the original task to hunt for a template can lead to distractions. Perhaps an incoming email grabs your attention, or a note in OneNote reminds you of a different task entirely and makes you work on another item altogether. These interruptions not only delay the immediate task but can derail overall productivity.

One productivity tool I frequently use to help alleviate this issue is the Windows Clipboard (accessible by pressing Win + V). It allows you to quickly access a history of items you've copied, and even pin frequently used items for easy retrieval, even after a system restart. However, while helpful, this solution still introduces friction. Pinning items isn't the clipboard’s primary focus, and pinned items are tucked away at the bottom of the list, making them less accessible. Additionally, the clipboard offers no convenient way to quickly edit common fields within a template, such as adding a number or inserting a line of personalized text for a specific customer. I believe there are still better ways to implement and streamline this functionality.

These challenges could be avoided with a faster, more seamless way to insert and edit templates directly within the program you’re working in—without ever leaving your current context. That is exactly what I propose. 

# The Solution

To address the problems of repetitive typing, inefficient template management, and distracting context-switching, I propose a solution that seamlessly integrates clipboard functionality with customizable templates—all without ever leaving the app you’re working in. The goal is simple: less app switching, more focus.

This focus is central to the product’s design. Every window should remain small and unobtrusive, preserving the user's attention on their primary text workspace. Core functions—such as adding a new template or opening the template selection window—should be accessible through keyboard shortcuts, minimizing the time and effort required. The UI itself should be streamlined to reduce the number of clicks needed to select and insert a template.

Additionally, key quality-of-life features should be built in. Users should be able to add placeholder sections within their templates so that, upon selection, the tool prompts them to input specific text substitutions. Once completed, the updated template would be automatically copied to the clipboard and inserted into the active window for immediate use, further enhancing speed and reducing interruptions.

This seamless workflow not only saves time but also reduces distractions, helping users stay focused on their primary task without bouncing between multiple applications. This tool is especially valuable for roles like Support Engineers, who often rely on repetitive messaging when communicating with customers. Instead of breaking their workflow to retrieve templates from a separate app, users can access, edit, and insert frequently used text snippets instantly.

# Golden Path (with Video)

- The user identifies some text that they use frequently (sending emails, running a script command, etc)
- The user adds this text as a template by using a shortcut (currently ctrl + alt + c). The template item is now added to the tool.
-	In the tool, the user can click on the “…” button next to the template item, a text-editor screen will open, allowing the user to change the contents of what they’ve copied.
-	In the text-editor, you can make changes to the text size, color, font, and format, as well as change the background color. 
-	In the edit window, the user can select a part of the text and hit the “[-->x←--] button in the ribbon. This adds the corresponding [--> x ←] brackets around the highlighted text.
-	The next time the user needs to access the template, they hit the shortcut to open the template view (currently ctrl + alt + v)
-	The user selects the template they would like by clicking on it.
-	Now, when selecting the template, the tool detects which objects are wrapped with [--> x ←--] and asks you to make a substitution. 
-	You write down what you want to replace them with, hit OK, and now it’s in your clipboard with the [--> x ←--] sections replaced with the text you input.
-	The template is automatically selected and pasted where the cursor was last selected.

<video width="100%" controls>
  <source src="/images/PowerClipboardGoldenPath.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

# User Flows Diagram 

<img src ="/images/Advanced_Paste_User_Flows.png">
