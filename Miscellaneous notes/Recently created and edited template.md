
<%*
const dv = app.plugins.plugins["dataview"].api;

// Add as many filenames and queries as you'd like!
const fileAndQuery = new Map([
  [
    "Recently edited",
    'TABLE WITHOUT ID link(file.name) AS Note, dateformat(file.mtime, "ff") AS Modified FROM "content" WHERE file.name != "Recently edited" AND file.name != "Recent new files" AND file.name != "index" AND file.frontmatter.draft = false SORT file.mtime desc LIMIT 7',
  ],
  [
    "Recent new files",
    'TABLE WITHOUT ID file.link AS Note, dateformat(file.ctime, "DD") AS Added FROM "content" WHERE file.name != "Recently edited" AND file.name != "Recent new files" AND file.name != "index" AND file.frontmatter.draft = false SORT file.ctime desc LIMIT 7',
  ],
]);
await fileAndQuery.forEach(async (query, filename) => {
  if (!tp.file.find_tfile(filename)) {
    await tp.file.create_new("", filename);
    new Notice(`Created ${filename}.`);
  }
  const tFile = tp.file.find_tfile(filename);
  const queryOutput = await dv.queryMarkdown(query);
  const fileContent = `---\ndraft: false\n---\n${queryOutput.value}`;
  try {
    await app.vault.modify(tFile, fileContent);
    new Notice(`Updated ${tFile.basename}.`);
  } catch (error) {
    new Notice("ERROR updating! Check console. Skipped file: " + filename , 0);
  }
});

let fileLink = tp.file.cursor(); // Grabs the current file link or path
let shortLink = fileLink.replace("content/", ""); // Replace 'content/' with nothing
//tR = "[[" + shortLink + "]]"; // Output as a link
%>


