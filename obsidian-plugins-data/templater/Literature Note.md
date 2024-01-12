---
id: <% INDENT_ID = "NO-L" + tp.date.now("YYYYMMDDHHmmssSSS") %>
aliases: []
---
<%*
NOTE_TYPE = "literature";
NOTE_DIR = "/KMATH/" + NOTE_TYPE.charAt(0).toUpperCase() + NOTE_TYPE.slice(1) + " Notes/";
try {
	await tp.file.move(NOTE_DIR + INDENT_ID + " New " + NOTE_TYPE + " note");
} catch (e) {
	await tp.file.move(NOTE_DIR + INDENT_ID + " New " + NOTE_TYPE + " note " + tp.file.creation_date("YYYYMMDDTHHmmssSSS"));
}
-%>