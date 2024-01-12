---
id: NO-D20230820064734723-1.0
aliases:
  - NO-D20230820064734723-1.0
---
**Personal Management and Productivity System (Permaprost)**

# Definition of Terms

Paper note - All notes written on paper with an ink pen or pencil is considered a paper note.
YAML front matter - A structure for defining metadata on hypertext or markup files.
	Aliases: YFM
Zettelkasten note - A single unit or entity of note that is either one of three types in accordance to the Zettelkasten concept.
	Aliases: ZK note
Personal Knowledge Management
ISO 8601

+++

# Methodology

This document, note, or article, whichever way it is perceived, is recursive. The concepts and methods mentioned here can be applied to this entity.

+++

# Knowledge Management and Thought Collection (KMATH)

KMATH defines how knowledge, thoughts, ideas, and data are captured or collected, how are they compiled to a specific structure, and where are they stored.
Notes are assigned a unique ID as per INDENT with the root classification `NO` followed by variables that describe the medium of persistence and other classification mentioned below.
## Zettelkasten Note-Taking

Notes that follow the Zettelkasten flow.
### Fleeting Notes

Raw information or thoughts gathered or generated must be recorded in Fleeting Notes. Each record here can be written as raw as possible while permitting the use of jargons, abbreviations, contractions, slang or any other form of informal writing to scribe thoughts as quick and as raw as possible. A common scenario of usage is when sudden realization, an epiphany or random thoughts that are valuable are encountered and must be captured as raw and soon as possible to avoid loss of information.
### Fragmented Notes

Writing any atomic thought about something, information or definition falls under Fragmented Notes. Anything contained within must not deviate from the topic or reference anything, even something related to it. A Fragmented Note can evolve into a separate Literature Note when a deeper study into the thought or information is warranted and sufficient sources are found or encountered to back this study.
### Literature Notes

Writing deducted information, thoughts or ideas whenever consuming any literature, online content, multimedia or any medium of information transfer must be written in a Literature Note.
### Rationalized Notes

Writing summarized documents once sufficient information has been realized from Literature Notes, Fleeting Notes and Daily Journals will produce a Rationalized Note.
### Flow

An NO-E can evolve into an NO-F when trying to normalize, sanitize or even break down the raw information or thought from the NO-E. An NO-F can be evolved into a separate NO-L when a deeper study into the thought or information is warranted and sufficient sources are found or encountered to back this study. An NO-L can evolve into an NO-R when sufficient testing or real-world data provides insights or proof how a new information can be applied and turned into wisdom.
An NO-L can also be broken down into various NO-Fs when several information is presented in that NO-L that can be related or unrelated to each other and can be further divided into their atomic form.
## Auxiliary Note Types

Notes that may or may not follow the Zettelkasten flow.
### Daily Journal

A Daily Journal is a manifestation of a Fleeting Note. Information or thoughts generated or gathered throughout a day must be placed in a Daily Journal, and be recorded in a raw form. It is recommended to use a bullet format for each thought or event.
### Quick Notes

quick notes
### Illustrative Notes

These are notes
## Note Persistence

The following defines where notes are stored or written.
### Paper Notebooks

Notes written on a piece of paper are considered as Paper Notes. Generally, it is more recommended writing notes in a notebook to avoid the risk of losing information.
Paper Notes will have...
### Digital Formats

Notes created and stored in any computer are considered notes in Digital Format. All digital notes will have an INDENT root classification of `NO`. Plain-text formats are recommended due to interoperability and simplicity.

**Implementation**

As of writing (2023-08-21), Obsidian is used to store notes in Markdown (.md) format.

Only the following note types are possible when writing a note in digital format, followed by their INDENT definitions:

*Daily Journal*

```
INDENT DEFINITION
{
	"syntax": "??-J#",
	"root": "NO",
	"index": "iso8601date_YYYYMMDD"
}
```

*Fleeting Notes*

```
INDENT DEFINITION
{
	"syntax": "??-F#",
	"root": "NO",
	"index": "iso8601datetime_YYYYMMDDHHmmssS"
}
```

*Literature Notes*

```
INDENT DEFINITION
{
	"syntax": "??-L#",
	"root": "NO",
	"index": "iso8601datetime_YYYYMMDDHHmmssS"
}
```

*Rationalized Notes*

```
INDENT DEFINITION
{
	"syntax": "??-D#",
	"root": "NO",
	"index": "iso8601datetime_YYYYMMDDHHmmssS"
}
```
## Data and Information Security


# Structured Data

Data that is stored with a specific structure or format falls under this section.


Plain-text notes must not contain PII...

# Indexing and Identification (INDENT)

INDENT defines how identifiers are defined and assigned to various entities as uniquely as possible.
## Syntax Definitions
### Root classification
All IDs start with two alphanumerical characters that indicate root classification.

### Subclassification
Asterisks (\*) indicate a variable character for subclassifications that can also be perceived as a wildcard. Assigning an item to a root classification without any subclassification must fill wildcards with zero (0). 

### Variable
Dollar signs ($) indicate a variable defined by a formula or a list of possible values. 

### Index
Pound or hash signs (#) indicate where the indexing characters should begin.

### Delimiter
Various parts of an ID should be separated by a delimiter to define a clear and logical structure. The default delimiter is a dash (-) (45 in ASCII, U+002D in Unicode).

## Documented Root IDs

### 0T -- Test ID
Syntax: `0T*#`

Test IDs are meant to index test or temporary entities.

Subclassifications:
	`0TU#` - Unique strict
		Index values with this subclassification must have uniqueness, preferably by generating random data to reduce data retention overhead.
	`0TN#` - Non-unique
		Index values with this subclassification can have a loosely generated values for temporary use.

### TK - Task

**Jira-based TWM**
Syntax: `TK***-#`

Markdown-based TWM

### NB -- Paper notebook
Syntax: `NB-#`
Indexing variables can consist of alphabets that can denote the purpose or category of the notebook.

### NP -- Note on paper
Syntax: `NP-*#`

Subclassifications:
	`NP-F#` - ZK fleeting note written on paper
	`NP-L#` - ZK literature note written on paper
	`NP-D#` - ZK distilled/permanent note written on paper

Indexing:
	All `NP-*#` IDs must follow an incremental indexing. Several pages at the start of a paper notebook must be designated to contain the index table.
	The index table must be structured with the following columns:
		- ID
		- Pages
		- Description
	Each row in the index table must contain the notes that are instantiated.

Note Instantiation:
	A note can be created by writing any content, knowledge, thought or idea on a page. Make sure to reserve a space or some lines dedicated to note metadata.
+++

### NO -- Note on digital platforms
Syntax: `NO-*#`

Subclassifications:
	`NO-J#` - ZK fleeting note as a daily journal
		Indexes for NOJ notes must be a date and time in the format of `YYYYMMDD` implemented in JavaScript as per ISO 8601.
	`NO-F#` - ZK fleeting note
	`NO-L#` - ZK literature note
	`NO-D#` - ZK rationalized or permanent documentation note
	`NO-Q#` - Notes with structured data for quick lookups (quick notes)
	`NO-H#` - Hand-drawn or hand-written notes (convert all NOH to NOI)
	`NO-I#` - Illustrative notes

Indexes for notes with subclassification NOF, NOL and NOD must be a date and time in the format of `YYYYMMDDHHmmssS` implemented in JavaScript as per ISO 8601.
+++

### NT -- Note template
Syntax: `NT-#`

Indexes must be a date and time in the format of `YYYYMMDD`

### PW -- Prototyping wire
Syntax: `PW-{$type}{$color}{$length}-#`

Variable `{$type}`:
	`S` - Solid wire
	`N` - Connecting wire
	`J` - Jumper

Variable `{$color}`:
	`S` - Solid wire

Variable `{$length}`:
	The length of the wire in centimeters divided by 10.
	
### E0 - Coursera activities

### E1 - UE activities

### CR - Cloud computing resource
Syntax: `CR*#`

### TS -- Time states
Syntax: `TS*`

++++++

# Task and Workflow Management (TWM)

A task is an atomic entity of work or job that needs to be done.

## States

Tasks have different states that indicate their status and what action must be performed upon the task. 
- TS1_TO_DO
	 The task is queued for work.
- TS2_IN_PROGRESS
	 Work is being performed upon the task.
- TS3_DONE
	 The task is completed and requires no further work.
- TS4_FAILED
	 The task has failed under certain criteria, deadline, or standards and requires no further work.
- TS5_CANCELLED
	 The task has been cancelled and requires no further work.
- TS6_ARCHIVED
	The task is no longer relevant and the data or information is now trivial for references.
## Projects

Tasks can be grouped under Projects to set a clear goal for that group of tasks.
## Dependencies and Child Tasks

dependencies...
## Priority

TP1 - Urgent
TP2 - High
TP3 - Normal
TP4 - Low
TP5 - Trivial

## Software and Tools

As of writing, the primary software used to track all tasks is Jira. (2023-08-21)

**Identifier**

Each task is assigned an ID upon creation. Rules for this are defined under INDENT.

--

# Time Adherence Discipline (TAD)
- All activities related to a certain project, job or goal must be documented with a time sheet.
- Software currently used: Toggl Track
--

# Contact Relations Management (CRM)
- x
--

# Personal Budget Management & Financing (PENBUMF)

## Recursive Expenses

Expenses that are made per unit of time to keep or maintain a specific service or product are defined as Recursive expenses.

**Tracking**

All Recursive expenses are to be recorded as a structured data as per KBATH and INDENT. Recursive expenses will be assigned a unique ID with root classification FR, and thus each Recursive expense will be referred to as an FR (plural FRs) anywhere under this section for convenience.

```
INDENT DEFINITION
{
	"syntax": "??-$$$${yr_start}$${mo_rec}#",
	"root": "FR",
	"vars": 
	{
		"yr_start": 
		{
			"desc": "Year when the recursive expense started"
		},
		"mo_start": 
		{
			"desc": "Month when the recursive expense started"
		}
	},
	"index": "ai"
}
```

--

# Tools & Software Used
- Obsidian - knowledge management
- OneNote - where old notes are/obsolete
- Notion - ??
- Asana - prospect software for task management?
- Toggl Track - time tracking / productivity adherence

+++

# Version Control

Main sysdoc
```
INDENT DEFINITION
{
	"syntax": "??-X$$$$$$$$$$$$$$$$${dt_created}-MP${ver_num}.${mrev_num}",
	"vars": 
	{
		"dt_created": 
		{
			"desc": "Date and time created",
			"format": "YYYYMMDDHHmmssSSS"
		},
		"ver_num": 
		{
			"desc": "Version number",
			"format": "%d"
		},
		"mrev_num": 
		{
			"desc": "Minor revision number",
			"format": "%d"
		}
	}
}
```

Addendums
```
INDENT DEFINITION
{
	"syntax": "NO-D$$$$$$$$$$$$$$$$${dt_created}-MP${ver_num}.${mrev_num}-${ad_num}",
	"vars": 
	{
		"dt_created": 
		{
			"desc": "Date and time created",
			"format": "YYYYMMDDHHmmssSSS"
		},
		"ver_num": 
		{
			"desc": "Associated sysdoc version number",
			"format": "%d"
		},
		"mrev_num": 
		{
			"desc": "Associated sysdoc minor revision number",
			"format": "%d"
		},
		"add_num": 
		{
			"desc": "Addendum number",
			"format": "%d"
		}
	}
}
```

# Addendums

[[Addendum 1 - Software-specific configurations]]