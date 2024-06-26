---
title: watlings
date: 2023-09-08T12:15:38+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1692552061072-ed2832e66403?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTQxNDY0OTB8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1692552061072-ed2832e66403?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE2OTQxNDY0OTB8&ixlib=rb-4.0.3
---

# [EmNudge/watlings](https://github.com/EmNudge/watlings)


<div align = center >

# Watlings

Learn the WebAssembly Text Format  
by fixing a bunch of small programs!

<br>

[![Button Roadmap]][Roadmap]

<br>

![Example Exercise]

</div>

<br>

> [!WARNING]
> This project is incomplete and in active development.  
> Feel free to help out by filing issues and creating PRs!


<br>
<br>

## Usage

This project uses **[Node 16+]** & **[NPM]** for compilation and testing.

<br>

Clone the repository and install dependencies with:

```sh
git clone git@github.com:EmNudge/watlings.git
cd watlings
npm install
```

<br>

Test your answer to an exercise with the `start` command:

```sh
npm start 001_hello
```

<br>

If you'd like to view the solution to an exercise, use the `solve` command:

```sh
npm run solve 001_hello
```

<br>

## Using Wat2Wasm Directly ( Recommended )

For syntax highlighting and up-to-date builds, you can **optionally** use the official **[WebAssembly Binary Toolkit][WABT]** which will provide you with a `wat2wasm` CLI tool.

If it is found on your path as `wat2wasm`, it will be used instead of **[NPM WABT]**.

*While it is strictly optional, it can help with debugging.*

<br>

## Recommended Editor

We recommend using **[VSCode]** with the **[WATI]** extension.

This should provide syntax highlighting, intellisense, and other helpful features as you work through the exercises.

<br>

## Motivations

I've found just diving in to be the best way to build experience with programming. 

**[Rustlings]** & **[Ziglings]** have both had tremendous returns to my journeys with both languages.

WebAssembly (and by extension WAT) has a more sparse educational landscape than most and I was hoping to fill some of the gaps by building a project with the same sort of structure.

<br>

## Pedagogical Philosophy

Outlined here are some thoughts on what makes a good teaching experience.

### Typing Over Reading

The goal is to learn by doing. Comments on each file outline a task and some background. However, a lot about a language can be gleaned by its syntax alone. We should be adding **as little** explanation as possible. 

Occasional gaps in knowledge can be filled by consistent exposure to the syntax within different contexts. Certain things can therefore be learned without any mention.

Introduction text is superfluous. Words add visual noise, so we should be careful with our count. Coding itself should supplement ambiguities in the text.

If you find a text confusing or too verbose, **please create a discussion post**!

### Create Struggle

Studies have shown that one cannot learn effectively without effort. This applies to practically every domain of knowledge. These projects should be educational, not easy.

This does not mean we should make the education itself elusive. We should not make learning more difficult, but instead more intentional.

When introducing a lot of new syntax, keep the problem scope small, but force the user to read a bit. If the syntax is not new, increase the problem scope. Maybe many variations of the same task.

<br>

## Credits

- [rustlings](https://github.com/rust-lang/rustlings)
- [Ziglings](https://github.com/ratfactor/ziglings)


<!----------------------------------------------------------------------------->

[Example Exercise]:https://github.com/EmNudge/watlings/assets/24513691/a777c665-fd13-4422-a570-2d3669b0ee94

[NPM WABT]: https://www.npmjs.com/package/wabt
[VSCode]: https://code.visualstudio.com
[WATI]: https://github.com/NateLevin1/wati
[WABT]: https://github.com/WebAssembly/wabt
[Node 16+]: https://nodejs.org/en
[NPM]: https://www.npmjs.com/

[Roadmap]: https://github.com/users/EmNudge/projects/1

[Button Roadmap]: https://img.shields.io/badge/Roadmap-19A974?style=for-the-badge&logoColor=white&logo=openstreetmap

[Rustlings]: https://github.com/rust-lang/rustlings
[ziglings]: https://github.com/ratfactor/ziglings