# Joke Template
	- ## Joke Page
		- template:: Joke/Page
		  properties::
		  title::
		  alias::
		  rank::
		  categories::
		  tags::
		  language:: [[English]]
			- ## Content
			- ## Variants
			- ## References
				- A. Author, "Document title," *Webpage name*, Source/production information, [[Date of internet publication]]. [Format: Online]. Available: [link_to_page](link_to_page). [Accessed: [[Date of access]]].
				  template:: Reference/Web Page 
				  type:: [[Web Page]]
- # Reference Template
	- Please check [IEEE Reference-Guide (noted and saved at Notion)](https://www.notion.so/IEEE-c20f77097df448c49d1f6e0688a49880#9ccdd756473d4718b2b71c5eb694e11c) for further information.
	- ## Web Page
		- A. Author, "Document title," *Webpage name*, Source/production information, [[Date of internet publication]]. [Format: Online]. Available: [link_to_page](link_to_page). [Accessed: [[Date of access]]].
		  template:: Reference/Web Page 
		  type:: [[Web Page]]
	- ## Book
		- A. A. Author, *Title: Subtitle (in italics)*, Edition(if not the first), Vol.(if a multivolume work). Place of publication: Publisher, Year, page number(s) (if appropriate).
		  template:: Reference/Book
		  type:: [[Book]]
	- ## Notion Block
		- template:: Reference/Book/Quote (synced from Notion)
		  notion-ref:: link
		  page::
		  title::
		  
		  content
- # Query Template
	- ## Query Tag With Current Page (Only Works For Lowercase)
		- template:: Query/Pages With Tag (Current Page)
		  #+BEGIN_QUERY
		  {
		      :title [:h2 "All Pages"]
		      :query [:find (pull ?p [*])
		      :in $ ?cat
		      :where
		          (page-property ?p :categories ?cat)
		      ]
		      :inputs ["NSFW"]
		  }
		  #+END_QUERY