./re
##  Intro - Talk about

* Your name and role as `AI Innovation Lead` at AFS
	* seeded into the latest technical advancement and work closely helping Federal Agencies tackle and solve some of their most complex challenges by tapping into the power of AI
	* build and manage AFS repository of AI assets & accelerators. DeepSee which we are going to demo today is such an accelerator AFS has built in house to help with data extraction from documents
* 
##  Demo	

What DeepSee is?
* History of DeepSee - rooted in out years of experience in GenAI platforms and RAG implementations 


1. Briefly discuss the DeepSee User Interface and talk about:
	* Architecture:  
		* multi agents
		* specialized models
		* supported extractions
		* supported files
		* high accuracy of extraction 90-100%
	* Supported files
2. Ingest `patent.pdf`
3. Talk and show proof of:
	- Barcode detection and extraction
	- Detection and extraction of molecular/chemical structures
	- Detection and extraction of tables and table data
	- Detection and extraction of mathematical formulas
	- Entity extraction and grouping based on semantic matching
	- Summarization
4. Talk about exporting extracted data to USPTO XML format and show:
	* texts
	* tables
	* chemistry
	* math formulas
5. Talk about now that we have data extracted, how can we put this data to work to create value. 
6. Leveraging LLM to consume extracted data
	1. Talk about markdown and the consolidated markdown
	2. Prompt AI to get answers on the extracted data:

```
How many pages are in this document?
```

```
how many molecular structures are in this document? 
```

```
provide in a tabular format with the following columns page, image id, smiles notation for all identified molecular formula
```

```
explain for someone who has limited chemical/molecular knowledge, what the molecular structure with SMILE code *C.*C(=*)N(*)C1=CC(=O)CCC1 is
```

```
how many unique molecular structures are in this document
```

7. Show a use case of Cross Reference where we can now use extracted molecular structure to search and match documents:
	1. Ingest `patent-partial.pdf` which is a partial of the document we just showed
	2. Show that 2 molecules were detected and pick one of the SMILES notations
	3. Jump to AI Assistant and prompt 
```
How many documents include references to molecular structure with SMILES notation *C.*C(=*)N(*)C1=CC(=O)CCC1
```


 8. Pick one of the documents USPTO provided and show complex table recognition