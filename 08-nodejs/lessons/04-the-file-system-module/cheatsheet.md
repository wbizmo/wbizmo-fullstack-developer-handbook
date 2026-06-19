# Lesson 04 Cheatsheet

Import:

    import fs from "node:fs/promises";

Read:

    await fs.readFile()

Write:

    await fs.writeFile()

Append:

    await fs.appendFile()

Delete:

    await fs.unlink()

Create folder:

    await fs.mkdir()

JSON parse:

    JSON.parse()

JSON stringify:

    JSON.stringify()

Key takeaway:
    fs lets Node.js interact with files and folders.
