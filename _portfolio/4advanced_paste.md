---
title: "Advanced Paste Clipboard for Windows"
excerpt: "Clipboard and template tool for Windows as a part of the Microsoft PowerToys project."
collection: portfolio
---

Advanced Paste is a productivity tool designed to reduce context-switching in repetitive communication tasks, like emails. Developed in collaboration with the Microsoft PowerToys team, who are committed to bringing power users a set of open source tool packages for productivity improvements.

**The Problem**
- 28% of office time is spent on email.
- Existing tools require context switching.
- Leads to cognitive overload and inefficiency.

**The Solution**
- Seamless integration of clipboard and templates.
- Less app switching, more focus.
- Great for roles like Support Engineers with repetitive messaging needs.

**Golden Path (with Video)**

•	The user identifies some text that they use frequently (sending emails, running a script command, etc)
•	The user adds this text as a template by using a shortcut (currently ctrl + alt + c). The template item is now added to the tool.
•	In the tool, the user can click on the “…” button next to the template item, a text-editor screen will open, allowing the user to change the contents of what they’ve copied.
•	In the text-editor, you can make changes to the text size, color, font, and format, as well as change the background color. 
•	In the edit window, the user can select a part of the text and hit the “[-->x←] button in the ribbon. This adds the corresponding [--> x ←] brackets around the highlighted text.
•	The next time the user needs to access the template, they hit the shortcut to open the template view (currently ctrl + alt + v)
•	The user selects the template they would like by clicking on it.
•	Now, when selecting the template, the tool detects which objects are wrapped with [--> x ←] and asks you to make a substitution. 
•	You write down what you want to replace them with, hit OK, and now it’s in your clipboard with the [--> x ←] sections replaced with the text you input.
•	The template is automatically selected and pasted where the cursor was last selected.

<video width="100%" controls>
  <source src="/images/PowerClipboardGoldenPath.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

[View Project on Github](https://github.com/diogoviveiros/EnhancedClipboardWPF)
