---
layout: archive
title: "AI-Native Teaching: My New Course Development and Maintenance Workflow"
permalink: /ai-native-teaching/
author_profile: true
---

{% include base_path %}

*November 11, 2026*

This semester marks the first of what I think of as my AI-native era of teaching. I ran my [Agentic AI for Business Applications](https://de4liu.github.io/agentic-ai-course-public/) course (IDSC 4590) on an agentic workflow: everything students see, from the syllabus to the slide decks to the Canvas pages and activity handouts, starts as plain text in a git repository, and a coding agent does most of the production work under my control. There is a certain symmetry in teaching agentic AI with agentic AI, but that is not the point of this piece. The point is what the workflow did to my work as a teacher: where it freed me, where it still needs me, and what it taught me about teaching itself.

## The setup

The core idea is simple. The course lives in a git repository as markdown and YAML: session plans, lecture outlines, assignment specs, rubrics, activity handouts, the syllabus. Canvas is a publish target, not the place where content lives. A coding agent (Claude, Cursor, Devin, pick your favorite) works in the repo the way a very fast, very literal assistant would: drafting pages, building decks, assembling modules, checking consistency.

The power is not any single feature. It is that *everything* is AI-powered but human-gated, inside one integrated workflow. I am not juggling separate tools for slides, pages, assignments, and quality checks; the same agent and the same source of truth drive all of them. Just as important, I want the AI to see the whole course: the source documents in the repository and the live state on Canvas, so it always works with full and proper context. That is what maximizes AI's strengths in discipline, scaling, and consistency. This, to me, is what AI-native means.

Two guardrails make it safe enough to trust in a live course. Nothing becomes student-visible without my review and approval: the agent proposes, I decide; or I propose, the agent implements, and I approve or ask it to revise. And student information never enters the agent's context or the repository. Rosters, submissions, and grades live outside the workspace entirely. Human judgment stays in the loop by design, not by habit.

## What I am most proud of: production quality

The surprise was not speed, it was quality.

**Markdown in, a designed deck out.** Lecture outlines render through a customized Marp pipeline into Carlson-styled slide decks that look like a designer made them. The deck is a text file I can diff and version, and the output is better than what I used to produce by hand in PowerPoint.

<figure>
  <img src="{{ base_path }}/images/ai-native-teaching/deck-title-slide.png" alt="Generated title slide for Week 3, Session 1" style="width:49%; display:inline-block; vertical-align:top;">
  <img src="{{ base_path }}/images/ai-native-teaching/deck-session-outline.png" alt="Generated session outline slide" style="width:49%; display:inline-block; vertical-align:top;">
  <figcaption>Two generated slides: the session title slide and the "where we go today" outline.</figcaption>
</figure>

**Figures on demand.** Course diagrams and illustrations are AI-generated SVGs made to my specifications. When a concept needs a picture, I describe the picture.

<figure>
  <img src="{{ base_path }}/images/ai-native-teaching/deck-svg-diagram.png" alt="Slide with an AI-generated SVG diagram of an agent-directed workflow" style="width:80%;">
  <figcaption>An AI-generated diagram, drawn to spec, explaining an agent-directed workflow.</figcaption>
</figure>

**Accessibility by default.** Decks and pages are checked against WCAG before they ever reach students; accessibility went from an afterthought to a build step that runs every time.

**Beautiful, consistent Canvas pages.** Course pages render from the same source, and consistency checks catch drift and orphaned objectives in seconds.

<figure>
  <img src="{{ base_path }}/images/ai-native-teaching/canvas-instruction-page.png" alt="Generated Canvas instruction page" style="width:49%; display:inline-block; vertical-align:top;">
  <img src="{{ base_path }}/images/ai-native-teaching/canvas-week-overview.png" alt="Generated Canvas week overview page" style="width:49%; display:inline-block; vertical-align:top;">
  <figcaption>Two Canvas pages rendered from the same markdown source: a setup instruction page and the week overview.</figcaption>
</figure>

<figure>
  <img src="{{ base_path }}/images/ai-native-teaching/sample-syllabus.png" alt="Top of the generated syllabus page" style="width:80%;">
  <figcaption>The syllabus is generated from the same source of truth as everything else.</figcaption>
</figure>

## Where the speed is: the mundane

The unglamorous work is where the hours came back. Installation instructions for student tools. Activity instructions and handouts. Creating and modifying assignments in batch. Updating a page because a schedule shifted. Each of these used to be a small chore that ate evenings in aggregate; now it is minutes of review.

It is also built to generalize. One codebase powers the tooling, and the kit is course-agnostic: a new course gets its own repository, and custom deck and page templates can be added without touching the tooling itself.

## The judgment layer: where my hours still go

I assumed AI would replace most of this work. It did not, and the reason matters.

Even the best models cannot make the nuanced judgment calls when it comes to substantive content or how it is organized. They still produce things that are incomprehensible, or fluent but not quite substantiated. Deciding which concept deserves the lecture, which frame will land for this cohort, whether an activity actually serves the objective: that is still mine, and I do not expect that to change soon.

What changed is *how* I author. I no longer touch PowerPoint or Word directly. I work through verbal instructions and chat, rarely editing a document myself. I still spend hours preparing each session, but the hours go to refining the deck's argument and the lesson design until I am satisfied, not to production. My teaching is AI-augmented, not AI-replaced.

## Where AI taught me

The unexpected part is how much I learned back.

The agent taught me *content*: ideas and framings I had not encountered. More surprisingly, it taught me *pedagogy*: activity formats I did not know how to design before. This course now runs build sprints, a structured debate, failure-mode analyses, red-teaming exercises, and a showcase, and it is far more experiential and interactive than anything I have taught before. It also helps me estimate activity timing, which changed how I plan a session.

And working this way forced a useful discipline on me. Objectives, rubrics, and course rules have to be written precisely enough for an agent to use them. That precision turned out to improve the course design itself.

## Where this is going

Honest status: this is an in-progress project. I am still refining the tooling and expanding what it can do, and a git-based workflow like this is not for every teacher today; the technical barrier is real.

But the *pattern* does not require a technical teacher. One source of truth, an agent that proposes and a teacher who approves, quality checks built into the pipeline: none of that inherently demands that the instructor write code. It demands better tooling. I am thinking about how to make this kind of framework available to every instructor. It is too early for details, but the direction is clear to me.

The same discipline, bounded autonomy with human approval and quality built in, is what I believe AI in the classroom needs broadly. It is also the philosophy behind [SmartPAL](https://www.smartpal.org), my work on AI assistants for learning and teaching.

