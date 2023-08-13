properties::
alias:: GA

	- query-sort-by:: page
	  query-sort-desc:: true
	  query-properties:: [:page :created-at]
	  #+BEGIN_QUERY
	  {:title "Pages in last 2 days"
	  :query [:find (pull ?p [*])
	  :in $ ?today
	  :where
	  [?p :block/created-at ?d]
	  [(- ?today 172800000) ?start]
	  [(>= ?d ?start)]
	  [(<= ?d ?today)]
	  ]
	  :inputs [:right-now-ms]}
	  #+END_QUERY
-