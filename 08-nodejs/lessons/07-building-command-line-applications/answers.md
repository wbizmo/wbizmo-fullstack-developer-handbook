# Lesson 07 Answers

1. Command Line Interface.
2. An array of command line arguments.
3. process.argv[2].
4. git, npm, node.
5. It has file system access and good package tooling.
6. An instruction passed to the CLI.
7. An option that modifies command behavior.
8. JSON file.
9. A Node.js script.
10. To guide users.

## Mini Project Solution

notes-cli.js

    import fs from "node:fs/promises";

    const command = process.argv[2];
    const value = process.argv[3];

    async function readNotes() {
      try {
        const content = await fs.readFile("notes.json", "utf8");
        return JSON.parse(content);
      } catch {
        return [];
      }
    }

    async function writeNotes(notes) {
      await fs.writeFile(
        "notes.json",
        JSON.stringify(notes, null, 2)
      );
    }

    if (command === "add") {
      const notes = await readNotes();

      notes.push({
        id: Date.now().toString(),
        text: value
      });

      await writeNotes(notes);

      console.log("Note added");
    } else if (command === "list") {
      const notes = await readNotes();

      notes.forEach((note) => {
        console.log(`${note.id}: ${note.text}`);
      });
    } else {
      console.log("Usage:");
      console.log("node notes-cli.js add \"Your note\"");
      console.log("node notes-cli.js list");
    }
