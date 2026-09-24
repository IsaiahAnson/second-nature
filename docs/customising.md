# Customising

The whole app is one file. These are the places most worth knowing about, in the order they appear.

## Look

- **Colour tokens** live in the first `:root` block of the `<style>` element, with a light-theme override just below it. The five section colours are `--s0` to `--s3` plus `--accent`; each nav group and page header picks one with `style="--g:var(--s1)"`.
- **Type** comes from two Google Fonts links at the top of the file: Bricolage Grotesque for display, IBM Plex Sans and Mono for text and figures, Fredoka and Atkinson Hyperlegible for the Snowball. Swap the links and the `--display`, `--body` and `--mono` tokens together.
- **Motion** honours the system reduced-motion setting and has its own toggle in the header. New animations should sit inside `@media (prefers-reduced-motion: no-preference)` and be switched off under `:root[data-motion="calm"]`.

## Content

- **Starter chunks:** the `STARTERS` array at the top of the main script. Each entry has `id`, `name`, `domain`, `gist`, `metaphor`, `useWhen`, `notWhen`, `links` (ids of related chunks) and `cards` (question and answer pairs). They are added to a fresh install only.
- **Quests:** `DEFAULT_QUESTS`, seeded once. Each is `[id, name, category, unit, goal, buff]`; categories are `body`, `home`, `work` and `mind`.
- **Review gaps:** `GAPS`. **Prediction chips:** `PRED`. **Scores and their labels:** `SCORES`.
- **The guide** on the Recall page ("How to use Second Nature") is plain markup in `#guide`.
- **Method** and **Motivation** are reference pages inside `<template id="methodTpl">` and `<template id="motivTpl">`, each with its own CSS and script, rendered into a shadow root so their styles stay separate.

## Adding a page

1. Add a `<button class="tab" ... data-act="tab" data-tab="NAME">` in the nav (inside a `.tgrp` group, or on its own).
2. Add a `<section class="view" id="view-NAME" ...>` in `<main>`.
3. Add `NAME` to the two tab lists in the main script (the one in `setTab` and the one that restores the last tab at boot), and a `renderNAME()` call in `renderAll()`.

## Storage

`store` is the only thing that talks to storage. It has two implementations, `dbStore` (the artifact database) and `localStore` (this browser), chosen at boot. Add a new collection by watching it in `startGame` and reading it from `G` or `S`, and write it with `store.setDoc(collection, id, body)`.
