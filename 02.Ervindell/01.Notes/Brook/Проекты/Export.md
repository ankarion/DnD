
```dataviewjs
const folder = "01.Notes/Brook";
const files = app.vault.getMarkdownFiles().filter(f=>f.path.startsWith(folder+"/"));

files.sort((a,b) => a.name.localeCompare(b.name));

let markdown = "# Brook story\n\n";
markdown += "## Table of contents\n";

for (let file of files) {
    const chapterTitle = file.name.replace(".md", "");
    let slug = chapterTitle.toLowerCase();
    slug = slug.replace(/[^a-z0-9]+/g,"-");
    slug = slug.replace(/(^-|-$)/g, "");
    markdown += `- [${chapterTitle}](#${slug})\n`
}
markdown += "\n---\n\n";

for (let file of files) {
    const chapterTitle = file.name.replace(".md","");
    const content = await dv.io.load(file.path);

    markdown += `#${chapterTitle}\n\n`;
    markdown += `${content}\n\n`;
    markdown += "---\n\n";
}

dv.paragraph("````markdown\n"+markdown+"\n````");
```
