properties::
type:: tags

- query-sort-by:: page
  query-sort-desc:: true
  #+BEGIN_QUERY
  {
      :title [:h2 "All Pages"]
      :query [:find (pull ?p [*])
      :in $ ?current-page
      :where
          (page-property ?p :tags ?current-page)
      ]
      :inputs [:current-page]
  }
  #+END_QUERY
-