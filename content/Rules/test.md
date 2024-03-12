```dataviewjs
const fs = require('fs')
let pages = dv.pages('"Rules/Master/Character"');
// Loop through pages
for (let p of pages){
	if (p.tags.includes("Rule") != true){
		continue;
	}
  // dv.el("h2",p.file.name); // note title
  // dv.paragraph(dv.fileLink(p.file.name,false)) // link to note
  f = await dv.io.load(p.file.path);
  fs.writeFile("Output.md", f, (err) => {
	  if (err) throw err;
  });
  dv.el("article", f)// note body
}
```
