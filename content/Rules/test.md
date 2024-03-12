```dataviewjs
let pages = dv.pages('"Rules/Master/Character"');
// Loop through pages
for (let p of pages){
	if (p.tags.includes("Rule") != true){
		continue;
	}
  // dv.el("h2",p.file.name); // note title
  // dv.paragraph(dv.fileLink(p.file.name,false)) // link to note
  dv.el("article", await dv.io.load(p.file.path)); // note body
}
```
