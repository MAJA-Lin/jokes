properties::

- ## 雙關語
	- ### [[Homophonic]] 諧音
	- ### Homographic 同形異義
- query-properties:: [:page :tags]
  #+BEGIN_QUERY
  {
      :title [:h2 "All Pages"]
      :query [:find (pull ?p [*])
      :in $ ?tag
      :where
          (page-property ?p :tags ?tag)
      ]
      :inputs [:current-page]
  }
  #+END_QUERY