- Shows a random joke.
- #+BEGIN_QUERY
  {:title "Give me a random page!!!"
   :query [:find ?name
           :where
           [?b :block/name ?name]]
   :result-transform (fn [result]
                       [(rand-nth result)])
  :view (fn [result]
         [:div.flex.flex-col
          (**for** [page result]
            [:a {:href (str "/#/page/" page)} (clojure.string/capitalize page)])])
   :collapsed? false}
  #+END_QUERY
-