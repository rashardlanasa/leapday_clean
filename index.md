---
layout: default
mermaid: true
---

# The View from the Top 
A new composite image built from 15 satellite passes shows the Arctic and northern latitudes as you have never seen them before. 
>Image by Norman Kuring, NASA/GSFC/Suomi NPP. Caption by Michael Carlowicz. Suomi NPP is the result of a partnership between NASA, NOAA and the Department of Defense.

>Published June 22, 2012
>Data acquired May 26, 2012

[<img src="https://eoimages.gsfc.nasa.gov/images/imagerecords/78000/78349/arctic_vir_2012147_lrg.jpg" alt="" />](https://eoimages.gsfc.nasa.gov/images/imagerecords/78000/78349/arctic_vir_2012147_lrg.jpg)

# GitHub Branching 
<div class="mermaid">
gitGraph:
    commit "Ashish"
    branch newbranch
    checkout newbranch
    commit id:"1111"
    commit tag:"test"
    checkout main
    commit type: HIGHLIGHT
    commit
    merge newbranch
    commit
    branch b2
    commit
</div> 


[Solid Steel Radio Show: Mixed by DK, Strictly Kev, PC, The Butch Cassidy Sound System (Nov 22, 2004)](https://youtu.be/e_N4TYS1l60?t=4509)


    
# Mermaid Sequence Diagram: Blogging app service communication
<div class="mermaid">
sequenceDiagram
    participant web as Web Browser
    participant blog as Blog Service
    participant account as Account Service
    participant mail as Mail Service
    participant db as Storage

    Note over web,db: The user must be logged in to submit blog posts
    web->>+account: Logs in using credentials
    account->>db: Query stored accounts
    db->>account: Respond with query result

    alt Credentials not found
        account->>web: Invalid credentials
    else Credentials found
        account->>-web: Successfully logged in

        Note over web,db: When the user is authenticated, they can now submit new posts
        web->>+blog: Submit new post
        blog->>db: Store post data

        par Notifications
            blog--)mail: Send mail to blog subscribers
            blog--)db: Store in-site notifications
        and Response
            blog-->>-web: Successfully posted
        end
    end

</div>

# Water CoolEr 
<div class="mermaid">
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
</div> 

# [Server Procurement Takes Too Long: Causes and Effects](https://github.com/rudolfolah/mermaid-diagram-examples/blob/main/diagrams/cause-and-effect.md)
<div class="mermaid">
mindmap
root{{Server Procurement Takes Too Long}}
  (Material)
    not sure what hardware requirements to use as a baseline
    obsolete hardware specifications
    high demand for specific hardware components
  (Vendors)
    convoluted, slow billing process
    limited vendor options
    long lead times for hardware delivery
    inconsistent communication from vendors
  (People)
    too many approvals required
    unclear when costs for server are passed to client
    client is unwilling to procure server
      budget unavailable until milestone is met
      does not see the need for the server
      already has on premises servers
      client does not want to use public cloud infrastructure
    lack of dedicated procurement personnel
    miscommunication between teams
  (Systems)
    procurement is not automated
    outdated procurement software
    lack of integration between procurement and project management tools
    manual tracking of procurement status
</div>div>
# Class Diagram 

<div class="mermaid">
---
title: Django Watson Class Diagram
---
classDiagram
class SearchAdapter {
  fields
  exclude
  store
  __init__(model)
  prepare_content(content)
  get_title(obj)
  get_description(obj)
  get_content(obj)
  get_url(obj)
  get_meta(obj)
  serialize_meta(obj)
  deserialize_meta(obj)
  get_live_queryset()
}

class SearchContextManager {
  _stack
  __init__()
  is_active()
  start()
  add_to_context(engine, obj)
  invalidate()
  is_invalid()
  end()
  update_index()
  skip_index_update()
}

class SearchContext {
  __init__(context_manager)
  __enter__()
  __exit__(exc_type, exc_value, traceback)
  __call__(func)
}

class SkipSearchContext {
  __exit__(exc_type, exc_value, traceback)
}

class SearchEngine {
  list _created_engines$
  dict _registered_models
  str _engine_slug
  SearchContextManager _search_context_manager
  get_created_engines()$ list
  __init__(engine_slug, search_context_manager)
  is_registered(model) bool
  register(model, adapter_cls, **field_overrides)
  unregister(model)
  get_registered_models() list
  get_adapter(model) SearchAdapter
  cleanup_model_index(model)
  update_obj_index(obj)
  _post_save_receiver(instance, **kwargs)
  _pre_delete_receiver(instance, **kwargs)
  _create_model_filter(models, backend) list
  _get_included_models(models) iter
  search(search_text, models, exclude, ranking, backend_name) Queryset
  filter(queryset, search_text, ranking, backend_name) Queryset
}

Exception <|-- SearchAdapterError
Exception <|-- SearchEngineError
Exception <|-- SearchContextError
SearchEngineError <|-- RegistrationError
SearchContextManager *-- SearchContext
SearchContext <|-- SkipSearchContext

</div>
Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
