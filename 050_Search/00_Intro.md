[[search]]
== Searching – the basic tools
## 搜索——基本的工具

So far, we have learned how to use Elasticsearch as a simple NoSQL-style
distributed document store -- we can throw JSON documents at Elasticsearch and
retrieve each one by ID. But the real power of Elasticsearch lies in its
ability to make sense out of chaos -- to turn Big Data into Big Information.

至目前，我们已经学会了如何使用elasticsearch作为一个简单的NoSQL风格的分布式文件存储器——我们可以将一个JSON文档扔给Elasticsearch，也可以根据ID检索它们。

This is the reason that we use structured JSON documents, rather than
amorphous blobs of data.  Elasticsearch doesn't only _store_ the document, it
also _indexes_ the content of the document in order to make it searchable.

*Every field in a document is indexed and can be queried*.  And it's not just
that. During a single query, Elasticsearch can use *all* of these indices, to
return results at breath-taking speed.  That's something that you could never
consider doing with a traditional database.

A _search_ can be:

* a structured query on concrete fields like `gender` or `age`, sorted by
  a field like `join_date`, similar to the type of query that you could construct
  in SQL

* a full text query, which finds all documents matching the search keywords,
  and returns them sorted by _relevance_

* or a combination of the two

While many searches will just work out of the box, to use Elasticsearch to
its full potential you need to understand three subjects:

[horizontal]

_Mapping_::     how the data in each field is interpreted
_Analysis_::    how full text is processed to make it searchable
_Query DSL_::   the flexible, powerful query language used by Elasticsearch

Each of the above is a big subject in its own right and we explain them in
detail in <<search-in-depth>>. The chapters in this section will introduce the
basic concepts of all three -- just enough to help you to get an overall
understanding of how search works.

We will start by explaining the `search` API in its simplest form.

.Test data

****

The documents that we will use for test purposes in this chapter can be found
in this gist: https://gist.github.com/clintongormley/8579281

You can copy the commands and paste them into your shell in order to follow
along with this chapter.

Alternatively, link:sense_widget.html?snippets/050_Search/Test_data.json[click here to open in Sense].

****