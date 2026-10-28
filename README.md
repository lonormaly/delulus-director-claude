# Delulus Director

Guidance for your course film.

Delulus Director helps students of the Delulus Productions filmmaking course develop a project from its first idea through story, screenplay, character and location choices, directing, performance, and editing. It applies the course guidance to the project context you provide in the conversation, helping you refine a Script Draft, revise a specific beat, prepare a scene plan, or work through a creative decision while keeping your approved choices in view.

Access is included for eligible course purchasers and requires signing in with an email linked to active course access. You can also ask about your current eligible enrollments. The plugin provides guidance and text preparation; it does not generate images, audio, or video, operate editing software, or make purchases. Projects are discussed in the current conversation, so bring your draft or project summary when continuing in a new chat.

## Install

In Claude Code, add this repository as a plugin marketplace, then install the plugin:

```
/plugin marketplace add lonormaly/delulus-director-claude
/plugin install delulus-director@delulus-productions
```

The first time Claude uses a Delulus Director tool, sign in with the email linked to your course access.

## Try asking

- "Help me turn a rough film idea into a compelling story."
- "Help me revise a beat while preserving the choices I have approved."
- "Which of my course enrollments currently give me Director access?"

## What this plugin contains and connects to

- **One skill**, `course-routing`, which tells Claude which course stage a request belongs to and how to read the course guidance completely and currently.
- **One remote MCP server**, `delulus-director`, at `https://director.delulus.productions/director/mcp`. It is operated by Delulus Productions and exposes three read-only tools:
  - `director_guidance` returns the course reference material for one stage (story, screenplay, characters, directing, performance or editing), in parts.
  - `director_visual_examples` returns 1–3 original, AI-generated course illustrations of camera, framing and focus choices, with captions and hosted image links.
  - `course_access` returns the signed-in student's current eligible enrollments (cohort, tier and course language).
- **Sign-in:** the first tool call opens an OAuth sign-in at `director.delulus.productions`. You confirm your email with a one-time code and approve access. Only an email with active course access can connect.
- **What is sent:** when Claude calls a tool, the server receives the requested stage and part number, the requested illustration IDs and caption language, or the optional enrollment ID, together with your sign-in token. Your conversation, files and drafts are not sent to the server by these tools.

The plugin runs no local code, hooks or scripts, and it installs no packages.

## Support, privacy and terms

- Support and course access: [course@delulus.productions](mailto:course@delulus.productions)
- Website: https://delulus.productions/director
- [Privacy policy](https://delulus.productions/course/privacy?lang=en)
- [Terms of service](https://delulus.productions/course/terms?lang=en)
