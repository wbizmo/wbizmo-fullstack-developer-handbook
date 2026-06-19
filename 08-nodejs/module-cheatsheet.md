# Node.js Fundamentals Module Cheatsheet

Run:

    node app.js

Initialize:

    npm init -y

Install:

    npm install package

Module import:

    import fs from "node:fs/promises";

Read file:

    await fs.readFile("file.txt", "utf8");

Write file:

    await fs.writeFile("file.txt", "Hello");

Path:

    path.join("data", "file.json");

Env:

    process.env.PORT

Events:

    emitter.on("event", callback);
    emitter.emit("event", data);

CLI:

    process.argv

Dev script:

    npm run dev
