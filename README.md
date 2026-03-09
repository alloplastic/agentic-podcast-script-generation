# Agentic Podcast Script Generation
A multi-stage AI writing process, implemented as LLM prompts for Claude Cowork but adaptable to other environments as well.

Based on the process used to create the futurist podcast [Friday Farsight](https://sheldonpacotti.com/friday-farsight).

# Instructions

Using these prompts is *almost* as easy as pointing Claude Cowork at this folder and copy-pasting the prompt in /Prompts/Write_Podcast.txt. However, there are a few tweaks that need to be made to the files, as well as some nuance to the process that won't be obvious to everyone. See the following walkthrough for more detail.

## Duplicate This Folder

Sounds simple, but if you checked out the repository with a "git clone" command, then you have some extra files in a top-level hidden .git folder you don't need. If you're not familiar with Git, you'll want to download the project from GitHub with the "Code --> Download ZIP" option. If you *are* familiar, then you probably don't need help with this issue, and Claude may in fact not care.

## Customize the Prompts

The prompts are ready to go except for two sections that need to be revised

### Prompt: Initial Draft

You'll need to define your own podcast concept and speaking style. You do this in /Guidelines/Initial_Draft_Guidelines.txt, which is the one file with specific language for the Friday Farsight podcast. Use this as a template for your own podcast.

Within this writeup is a list of techniques for achieving "naturalness." See the couple of examples there to get an idea of what kind of speech patterns to give your hosts.

NOTE: the Initial_Draft_Guidelines.txt file should only need to be modified once. If you're getting the style of speech you want, and the hosts seem knowledgeable about the podcast they are hosting, then this file can remain the same for every eposide.

### Prompt: Write a Podcast

In the main prompt, the one that gets pasted into Claude Cowork, I like to add a sentence or two on the overall concept of the week's episode, just to ground the LLM in the mission. E.g., "Could you help me write a podcost episode for this week's prediction about faster-than-light spacecraft?"

For each episode, you'll want to update this language in /Prompts/Write_Podcast.md.

NOTE: this is the only actual prompt to be sent to Claude Cowork. It directs the AI to follow the instructions in the various "guideline" prompts (/Guidelines folder).

### Example Dialogue (Optional)

Many of the guideline prompts in /Guidelines contain example dialogue, set off by "example" tags. This dialogue, mostly hand-written by me, comes from the Friday Farsight podcast. You're welcome to keep feeding those examples to the LLM, but you may want to (or need to) replace those in order to achieve your own particular podcast style.

## Add Sources

This generator was designed to work from one or more source articles, e.g. .DOCX, .TXT, or similar files. Put these in the /Sources folder, where Claude will be instructed to look for them.  Something on the order of a rich encyclopedia article or Wikipedia page would be about the minimum needed for a 15-minute podcast.

## Generate the Podcast Script

Set up Claude Cowork to work on this top-level folder, so that it can access all of the files in this project. Copy-paste the text in the "# Prompt" section of /Prompts/Write_Podcast.md into Claude Cowork. Send that text to Claude (or Opus etc.), and the multi-step agentic writing workflow should run.

Multiple drafts will be written to the /Drafts folder.

## Generate Audio

For the task of synthesizing the script's audio, I vibecoded a basic, clunky app in Google AI Studio. You can do something similar, or build off of [mine](https://ai.studio/apps/74263596-0878-4d06-9e75-acd2752f91c0). (Not user friendly -- see below for quirks.)

Or, easier but more expensive, sign up for a platform like ElevenLabs or Wondercraft.ai, and edit /Guidelines/Podcast_Script_Format.txt to match the import format of your chosen platform.

Notes on my vibe-coded audio generator app:

  * The above link gives you access to the code, but you need to provide your own Google text-to-speech API key to make use of it (otherwise, I would get billed for your audio); see the Google AI Studio docs, or favorite LLM, for instructions on how to do that
  * To use the app, which appears in "Preview" in AI Studio, you may need to refresh and accept the browser's request to access the clipboard
  * My workflow: Copy 30-40 lines of the script at a time (from the output in the /Drafts folder), click the "Import from Clipboard" button (script will then appear in UI), select voices for the hosts, click the "Generate Audio" button, wait a while, then use the newly visible buttons to play and/or download the audio file
  * Disclaimer: I've tested no other workflows but this, not even the "generate script" feature, which the LLM created on its own initiative. There are no niceties like editing the script live or copy-pasting, and I haven't looked closely at the error handling. So, use at your own risk.
  * That 30-40 line rule is because the text-to-speech model tends to get overloaded with more dialogue than that, meaning that it starts to make more errors. Depending on how verbose your hosts are, the exact line limit may vary.
  
### Digression

I've also considered replacing the audio-gen UI with a prompt. This would rely on Claude Cowork using an MCP server to connect to ElevenLabs or another API to synthesize individual lines and then stitch them together, using a specific local file format that would let us do retakes and re-cut the final show via editing text files and prompting Claude. An intriguing possibility, prefiguring the death of application software, but I seem to be getting a decent workflow out of my vibe-coded app.

And, actually, these text-to-speech models are now accepting sets of lines together, which are used to generate a seamless back-and-forth with good emotional flow. Would probably be very hard to decouple into a file-by-file system on a local hard drive.
