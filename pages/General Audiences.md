properties::
alias:: GA

	- query-sort-by:: page
	  query-table:: false
	  query-sort-desc:: true
	  query-properties:: [:alias :ga]
	  #+BEGIN_QUERY
	  {
	    :title [:b "General Audiences"]
	    :query [
	      :find (pull ?p [*])
	    ]
	  }
	  #+END_QUERY