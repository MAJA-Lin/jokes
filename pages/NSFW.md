properties::
alias:: Not Safe For Work

-
- #+BEGIN_QUERY
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