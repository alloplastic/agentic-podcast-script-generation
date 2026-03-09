# Cowork Prompt for Writing a Podcast

## Instructions

Copy-paste everything AFTER "# Prompt" into Claude Cowork, with Claude Cowork pointed at the parent folder of this one. (See the README.md" file there for more detailed instructions.)

Note that you'll probably want to slightly edit the top-level instruction for every episode, in order to ground the LLM in the main idea. Look for the several phrases below set off with "********".

## Background

This prompt translates an article or articles into a conversational podcast. Richness and originality are achieved by directing the model to revise the script multiple times, improving first the content and then the style of the dialogue. It is intended to be used with Claude Cowork on a folder of files that has a specific structure -- presumably the structure within which you found this file.

# Prompt

Good evening.  Could you please help me create a lively podcast on ******** how humanity may one day replace plastic as the dominant material ********?
 
Let's follow a rigorous writing process, proceeding from brainstorming to a first draft and then through two revisions to a polished script.  This script will be voiced by synthesized actors via the Google text-to-speech API, and then will be published for the tens of millions of intellectually curious podcast listeners in the English-speaking world.

Please follow this process:

1. Following the guidelines in /Guidelines/Reflection_Guidelines.md, think deeply about the ******** prediction ********  described in the document(s) in the /Sources folder, searching your heart for what in the ******* prediction ********  will be most moving or intellectually stimulating to other human beings. Take notes in /Drafts/Reflections.txt, developing your own sharp point of view that will help you write a strikingly impactful discussion.

2. Write a first draft, following the guidelines in /Guidelines/Initial_Draft_Guidelines.md.  Base the podcast content on the document(s) in the /Sources folder and use your notes in /Drafts/Reflections.txt to inform where to place emphasis, where to expand, where to pit opposing views against each other, etc.  Compose the script in the Google text-to-speech format defined in /Guidelines/Podcast_Script_Format.txt and write the file to disk in /Drafts/Draft.01.txt.

3. Revise the script with a focus on embellishment and completeness, following the guidelines in /Guidelines/Embellish_Guidelines.md.  Save the new draft in /Drafts/Draft.02.txt.

4. Perform a finer grained revision, aiming at polish, uniqueness, and indelibility, following the guidelines in /Guidelines/Polish_Guidelines.md. Once again, refer to your notes in /Drafts/Reflections.txt to help identify opportunities to more powerfully connect with the audience. Save the new draft in /Drafts/Draft.03.txt.
