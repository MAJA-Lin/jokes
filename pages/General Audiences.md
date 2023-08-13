properties::
alias:: GA

	- query-sort-by:: page
	  query-table:: false
	  query-sort-desc:: true
	  query-properties:: [:alias :ga]
	  #+BEGIN_QUERY
	  		  {
	  		   :query [:find (pull ?b [*])
	  		        :where
	  		        [?b :page/properties ?pprops]
	  		        [(get ?pprops:ga"nil") ?bs]
	  		        [(not= ?bs "nil")]]
	  		  :result-transform (fn [result]
	  		      (sort-by (fn [h]
	  		        (get-in h [:block/properties :ga])) result))
	  		  }
	  #+END_QUERY