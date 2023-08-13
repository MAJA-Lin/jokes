properties::
alias:: GA

- 普遍級
  query-properties:: [:page :tags :language]
- query-sort-by:: page
  query-sort-desc:: false
  query-properties:: [:page :tags]
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