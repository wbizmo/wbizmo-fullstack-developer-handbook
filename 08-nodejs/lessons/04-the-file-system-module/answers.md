# Lesson 04 Answers

1. fs.
2. Yes.
3. Reads a file.
4. Writes a file.
5. Adds content.
6. Deletes a file.
7. Store structured data.
8. Converts JSON text into JavaScript.
9. Converts JavaScript into JSON text.
10. Notes apps, configs, logs, storage.

## Mini Project Solution

notes-manager.js

    import fs from "node:fs/promises";

    async function addNote(
      note
    ) {
      const content =
        await fs.readFile(
          "notes.json",
          "utf8"
        );

      const notes =
        JSON.parse(content);

      notes.push(note);

      await fs.writeFile(
        "notes.json",
        JSON.stringify(
          notes,
          null,
          2
        )
      );
    }

    async function listNotes() {
      const content =
        await fs.readFile(
          "notes.json",
          "utf8"
        );

      console.log(
        JSON.parse(content)
      );
    }
