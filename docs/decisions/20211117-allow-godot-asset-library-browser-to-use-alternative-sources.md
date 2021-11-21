# Allow Godot Asset Library browser to use alternative sources

- Status: proposed <!-- draft | rejected | accepted | deprecated | superseded by -->
- Deciders: V-Sekai,
- Tags: V-Sekai,

## Context and Problem Statement

Godot Engine has a great asset library browser.

Why can't we reuse it for alternative Godot engine asset libraries?

This is a pattern used by package managers for long (npm, apt, pacman, f-droid, ...).

## Describe the proposed option and how it helps to overcome the problem or limitation

1. Add an alternative server
2. document the current api as an openapi schema.

## Describe how your proposal will work, with code, pseudo-code, mock-ups, or diagrams

1. Openapi schema for the official asset library api.
1. Elixir server implementation (using the current server as a reference implementation)
2. Patch to Godot Engine to add arbitrary asset libraries

## Positive Consequences <!-- optional -->

- allow teams working on a specific project to share common assets privately in a centralized location
- allow teams and individuals to create personal libraries with starter kits, templates, or common plugins that are reused from project to project
- enable alternative libraries to exist, to:
  -  short-circuit Godot's approval process
  -  curate a different selection with different standards (only the highest quality, or accepting even broken plugins, etc)
  -  curate plugins pertaining to a specific ecosystem (using a specific language, a specific API, ...) 
  -  group thematically or authorially related addons under one umbrella


## Negative Consequences <!-- optional -->

- Exposes Godot users to more abuse and/or vulnerabilities (mitigation: clearly warn users that by using a third party repository, they're responsible of the trust they put in
- Increases the complexity of the UI (mitigation: add alternative repositories in the main settings, or behind a de-prioritized buttin)
- Forces to write and maintain a spec for server changes, which can slow down the development of new features 

## Option graveyard: <!-- same as above -->

- Option: <!-- [List the proposed options no longer open for consideration.] -->
- Rejection Reason: <!-- [List the reasons for the rejection: (the Bad traits)] -->

## If this enhancement will not be used often, can it be worked around with a few lines of script?

- Creating a user-space plugin that uses an alternative repository is doable, but it'd be a lot of work, and wouldn't follow the same patterns or use the same widgets as the main library
 
## Is there a reason why this should be core and done by us?

The scope of writing a reference server, as well as maintaining documentation for the API and match it with the client makes this project a bit too complex to be maintained externally.

## References <!-- optional -->

- https://github.com/godotengine/godot-asset-library/blob/master/API.md

## Derivative License

Copyright (c) 2021 V-Sekai contributors.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
