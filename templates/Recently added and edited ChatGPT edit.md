<%*
const dv = app.plugins.plugins["dataview"].api;

// Add as many filenames and queries as you'd like!
const fileAndQuery = new Map([
  [
    "Recently edited",
    'TABLE WITHOUT ID link(file.name) AS Note, dateformat(file.mtime, "DD, T") AS Edited FROM "content" WHERE file.name != "Recently edited" AND file.name != "Recently created" AND file.name != "index" AND file.frontmatter.draft = false SORT file.mtime desc LIMIT 10',
  ],
  [
    "Recently created",
    'TABLE WITHOUT ID file.link AS Note, dateformat(file.ctime, "DD, T") AS Created FROM "content" WHERE file.name != "Recently edited" AND file.name != "Recently created" AND file.name != "index" AND file.frontmatter.draft = false SORT file.ctime desc LIMIT 10',
  ],
]);
await fileAndQuery.forEach(async (query, filename) => {
  if (!tp.file.find_tfile(filename)) {
    await tp.file.create_new("", filename);
    new Notice(`Created ${filename}.`);
  }
  const tFile = tp.file.find_tfile(filename);
  let queryOutput = await dv.queryMarkdown(query);

  // Remove "content/" from links in the result
  queryOutput.value = queryOutput.value.replaceAll("content/", "");

  const fileContent = `---\ndraft: false\n---\n${queryOutput.value}`;
  try {
    await app.vault.modify(tFile, fileContent);
    new Notice(`Updated ${tFile.basename}.`);
  } catch (error) {
    new Notice("ERROR updating! Check console. Skipped file: " + filename , 0);
  }
});
%>

