# Your Game Manual Website

This repository holds the files for your game manual. Every time you **commit** (save your changes to GitHub), a tool called DITA-OT turns your files into a website automatically.

**Your website's address** is in the **About** box on the right side of this page (on a phone, scroll down to find it). Bookmark it!

---

## 1. Open the editor

1. Go to this repository's page on github.com (the page you're reading now).
2. Press the **.** (period) key on your keyboard.

The editor, **github.dev**, opens in your browser. It looks like a word processor's file list on the left and your writing on the right. You don't need to install anything.

> If the period key doesn't work, change `github.com` to `github.dev` in the address bar and press Enter.

## 2. Know your files

| File or folder | What it is |
|---|---|
| `manual.md` | Your website's **menu**. It lists every page, in order. |
| `topics/` | Your **pages**. Each page is one `.md` file, sorted into folders. |
| `images/` | Your **pictures**. |
| `design.md` | Your website's **look**: theme, colors, and fonts. |

The website builder lives in a hidden `.github` folder. The editor hides it so you don't change it by accident.

The pages that come with this repository are a short sample manual for an invented game called **Skyharbor**. They show each kind of page, a menu with sections, a picture, and links between pages. Look at them to see how everything works, then replace them with your own game.

## 3. Write a page (a "topic")

Every page starts with a title line: a `#`, a space, the title, and the **topic type** in curly brackets.

```
# Set Up the Sky Map {.task}
```

There are three topic types:

**Concept** `{.concept}` explains *what something is*. Use paragraphs. Use `##` for section headings.

```
# How to Win {.concept}

At the end of the eighth round, the captain with the most renown wins.

## Earning renown

Contracts are usually the largest source of renown.
```

**Task** `{.task}` explains *how to do something*. Use a numbered list, with **one instruction per number**. To add details to a step, use a bullet point indented under it.

```
# Set Up the Sky Map {.task}

Do this before the players choose their colors.

1. Unfold the sky map and place it in the middle of the table.
2. Shuffle the contract cards.
    - Place them face down beside the map.
3. Place the storm marker on the region numbered 7.

The sky map is ready.
```

**Reference** `{.reference}` holds *facts to look up*, usually in a table.

```
# Scoring Table {.reference}

| Source | Renown |
|------|------|
| Dock | 2 each |
| Upgrade | 1 each |
```

### Add a new page

1. In the file list, right-click the folder the page belongs in (inside **topics**) and choose **New File**.
2. Name it with **lowercase letters and hyphens only**, ending in `.md`. For example, `sell-cargo.md`. No spaces!
3. Write or paste your content.
4. Add the page to your menu (next section). **A page that isn't in the menu won't appear on your website.**

## 4. Edit the menu (`manual.md`)

`manual.md` is a bulleted list of links. Each link looks like this:

```
- [The words shown in the menu](topics/folder-name/file-name.md)
```

To group pages under a heading, write the heading as a bullet **without** a link, then indent the pages under it by pressing **Tab**:

```
# Skyharbor Game Manual

- [Game overview](topics/about/game-overview.md)
- Setting up
    - [Set up the sky map](topics/setup/set-up-sky-map.md)
    - [Set up your player area](topics/setup/set-up-player-area.md)
- [Glossary](topics/help/glossary.md)
```

The first line, starting with `#`, is your website's title.

**Tip:** `manual.md` is the best way to get around your files. Hold **Ctrl** (Windows) or **Cmd** (Mac) and click any link in it to open that page.

## 5. Keep lots of pages organized

A full rulebook can turn into 50 or more pages. Folders keep that manageable.

**Make one folder for each section of your menu.** If your menu has a "Setting up" section, put those pages in `topics/setup/`. Then the file list looks like your menu, and each folder holds only a handful of files.

```
topics/
    about/
        game-overview.md
        how-to-win.md
    setup/
        set-up-sky-map.md
        set-up-player-area.md
    turns/
        round-overview.md
        sail.md
    help/
        glossary.md
```

- **Make a folder:** right-click **topics**, choose **New Folder**, and name it with lowercase letters and hyphens.
- **Move a page:** drag it onto a folder. The editor offers to update the links to it; choose **Yes**. If it doesn't, the builder still finds the page by its file name.
- **Close folders you aren't working in:** click the arrow next to a folder name. Click the **Collapse Folders** button at the top of the file list to close them all.

To find things quickly:

- **Open a page by name:** press **Ctrl+P** (Windows) or **Cmd+P** (Mac) and type part of the file name, like `sail`. Press Enter to open it.
- **Search every page:** press **Ctrl+Shift+F** (Windows) or **Cmd+Shift+F** (Mac) and type a word, like `storm`.
- **Search your website:** every page of your website has a search box at the top, so your readers can find any rule. Use it to check that someone looking for a word like "storm" would find the right page.
- **Check your list of pages:** the **Build report** on your website lists every page in your menu with its topic type. Compare it with your content inventory.

Give every page its own file name, even in different folders. If two files have the same name (like `setup/overview.md` and `turns/overview.md`), always write the full path to them.

## 6. Add a picture

1. Drag the picture file from your computer onto the **images** folder in the file list.
2. Rename it with lowercase letters and hyphens, like `sky-map.png`.
3. In your page, add this line where the picture should go:

```
![A short description of the picture](/images/sky-map.png)
```

Start the path with `/images/`, no matter which folder your page is in. The `/` means "start from the top folder of the repository."

The description is read aloud to people who use screen readers, so make it meaningful.

To link from one page to another, use the same kind of path:

```
See [Sail](/topics/turns/sail.md) for the rules.
```

## 7. Change your website's look (`design.md`)

Open `design.md` and change the words after the colons:

```
Theme: ocean
Style: glass
Main color: navy
Heading font: Merriweather
```

The instructions in `design.md` list every theme and setting.

**Choose your Start page.** Your home page has a **Start here** button for someone who has just opened the box and wants to play. In `design.md`, set `Start page:` to the menu item that player needs first, like `Start page: Set up the sky map`. Every page also ends with **Previous** and **Next** links that follow the order of your menu, so put your menu in the order a new player should read it. You can't break your website from this file: if the builder doesn't understand something, it uses the theme's normal setting and tells you in the build report.

## 8. Publish your changes (commit)

Your website **doesn't change until you commit.**

1. Click the **Source Control** icon on the far left. It looks like a branching line, and shows a number when you have changes.
2. Type a short message describing what you changed, like `Add the sail page`.
3. Click **Commit & Push**.
4. Wait about **two minutes**, then open your website and refresh the page.

Check the **"Last updated"** time at the bottom of any page on your website. If it shows the time of your latest commit, you're looking at the newest version. If not, wait a minute and refresh again.

## 9. If something goes wrong

The builder fixes small mistakes for you and builds your website whenever it can.

- **Build report:** the bottom of every page on your website has a **Build report** link. It lists anything that needs your attention, like a menu link that points to a file that doesn't exist, or a picture that's missing.
- **"Your website didn't update" email:** if the builder can't build your website at all, it opens an **Issue** in this repository, and GitHub emails you. The issue explains the problem in plain English. It closes by itself once you fix the problem and commit again.
- **The Actions tab:** at the top of this repository's page on github.com, **Actions** shows every build. A green check ✅ means it worked; a red ✖️ means it didn't. Click one to see its report.

---

## Tips for working with an AI

Paste these rules into your AI chat before asking it to convert a section of your rulebook:

```
Format your answer as Markdown DITA (MDITA) for a DITA-OT website:
- Start with one title line: "# Title {.concept}", "# Title {.task}", or "# Title {.reference}".
- Concept: explains what something is. Paragraphs, with "##" section headings if needed.
- Task: explains how to do something. A short intro sentence, then a numbered list
  with ONE instruction per number. Put extra details as "-" bullets indented under
  a step. Never put a paragraph, picture, or note inside a numbered step.
- Reference: facts to look up, in Markdown tables.
- Write one topic per answer. Don't add YAML front matter or HTML.
- Start picture paths with /images/ (like ![Sky map](/images/sky-map.png)) and links
  to other pages with /topics/ (like [Sail](/topics/turns/sail.md)).
- Above your answer, suggest a file name in lowercase-with-hyphens.md.
```

Remember: the AI is your assistant, not the author. Check every rule against the original rulebook.
