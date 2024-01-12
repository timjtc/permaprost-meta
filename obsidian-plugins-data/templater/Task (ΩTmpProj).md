---
description: 
status: TS1_TO_DO
due: 
priority: 
tags: 
aliases:
---
<%* 
// CONFIG: below are the only values you are allowed to change
PROJECT_METAFILE = "_twm_prj_meta_99";
PROJECT_ID = "99";
PROJECT_NAME = "ΩTmpProj";
JS_TIMEOUT = 75;
// END OF CONFIG

meta_file = await tp.file.find_tfile(PROJECT_METAFILE);
read_meta = await app.vault.read(meta_file);
var key = "last_id: ";
last_id = read_meta.substring(
    read_meta.indexOf(key) + key.length, 
    read_meta.lastIndexOf("\"")
).replace("\"", "");
int_next_id = parseInt(last_id) + 1;
NEXT_ID = int_next_id.toString();

INDENT_ID = "TK-" + PROJECT_ID + NEXT_ID;
TASK_DIR = "/TWM/Tasks/" + PROJECT_ID + " " + PROJECT_NAME + "/";

let desc = "New template task " + INDENT_ID;
let due = tp.date.now("YYYY-MM-DD");
let prio = "TP3_NORMAL";

setTimeout(() => { 
	app.fileManager.processFrontMatter(tp.config.target_file, frontmatter => { 
		frontmatter["description"] = desc
		frontmatter["due"] = due
		frontmatter["priority"] = prio
	})
}, JS_TIMEOUT); // the reason for the timeout is to let the template complete first

try {
	await tp.file.move(TASK_DIR + INDENT_ID);
	app.fileManager.processFrontMatter(meta_file, frontmatter => { 
		frontmatter["last_id"] = NEXT_ID
	});
} catch (e) {
	await tp.file.move(TASK_DIR + INDENT_ID + " " + tp.file.creation_date("YYYYMMDDTHHmmssSSS"));
}
_%>

# Remarks


# Dependencies and Child Tasks


# Related Notes

