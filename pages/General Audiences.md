properties::
alias:: GA

- query-properties:: [:page :tags :language]
- query-sort-by:: page
  query-sort-desc:: false
  #+BEGIN_QUERY
  {
      :title [:h2 "All Pages"]
      :query [:find (pull ?p [*])
      :in $ ?cat
      :where
          (page-property ?p :categories ?cat)
      ]
      :inputs ["GA"]
  }
  #+END_QUERY