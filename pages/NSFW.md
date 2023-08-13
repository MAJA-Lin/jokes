properties::
alias:: Not Safe For Work

- {{query (page-property :categories [[NSFW]]) (sort-by created-at desc)}}
  query-table:: true
  query-properties:: [:page :tags :alias :language]
  collapsed:: true
- #+BEGIN_QUERY
  {
      :title [:h2 "All Pages"]
      :query [:find (pull ?p [*])
          :in $ ?current-page
          :where
          [?p :page/properties ?prop]?current-page]
      ]
      :inputs [:current-page]
  }
  #+END_QUERY