Elastic Search Notes

Module 1 

Demo 1 - Download and install

ES requires Java 8.

java -version
echo $JAVA_HOME

If no Java then download and install from Oracle's website
http://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html

mkdir es-install
cd es-install/elasticsearch-5.3.0
./bin/elasticsearch

./bin/elasticsearch -Ecluster.name=loonycorn -Enode.name=first_node


Demo 2 - Cluster Health

http://localhost:9200

localhost:9200/_cat/health?v&pretty
http://localhost:9200/_cat/health?v&pretty

localhost:9200/_cat/nodes?v&pretty
http://localhost:9200/_cat/nodes?v&pretty


Module 2 

Demo 1 - curl and listing all indices 
curl http://www.google.com
curl http://www.google.co.in

curl -XGET 'localhost:9200/_cat/indices?v&pretty'
curl -XGET 'localhost:9200/_cat/nodes?v&pretty'



Demo 2 - Create an index
curl -XPUT 'localhost:9200/courses?&pretty'
curl -XGET 'localhost:9200/_cat/indices?v&pretty'

curl -XPUT 'localhost:9200/students?&pretty'
curl -XPUT 'localhost:9200/enrolled?&pretty'
curl -XGET 'localhost:9200/_cat/indices?v&pretty'

Demo 3 - Index and Query a document

curl -XPUT 'localhost:9200/courses/web/1?pretty' -d'
{
  "name": "React JS",
  "instructor": "Janani Ravi",
  "hours": "7.5",
  "lectures": "45",
  "certification": "no",
  "reviews": ["Great for beginners, step by step instructions", "Goes a little slowly, not meant for people who are looking for a quick overview", "Great explanations"]
}
'
curl -XPUT 'localhost:9200/courses/web/2?pretty' -d'
{
  "name": "Angular JS",
  "instructor": "Janani Ravi",
  "hours": "8",
  "lectures": "48",
  "certification": "no",
  "reviews": ["For angular 1.2, would like the latest version",  "Love the examples"]
}
'
curl -XPUT 'localhost:9200/courses/web/3?pretty' -d'
{
  "name": "PHP",
  "instructor": "Janani Ravi",
  "hours": "13",
  "lectures": "70",
  "certification": "no",
  "reviews": ["Love the explanations and the detail"]
}
'
curl -XPUT 'localhost:9200/courses/web/3?pretty' -d'
{
  "name": "PHP",
  "instructor": "Loonycorn",
  "hours": "13.5",
  "lectures": "69",
  "certification": "no",
  "reviews": ["Love the explanations and the detail"]
}
'

curl -XPUT 'localhost:9200/courses/programming/1?pretty' -d'
{
  "name": "Scala",
  "instructor": "Vitthal Srinivasan",
  "hours": "7",
  "lectures": "60",
  "certification": "no",
  "quizzes": "yes",
  "reviews": ["Loved the detail, great course for beginners"]
}
'

curl -XPUT 'localhost:9200/courses/programming/2?pretty' -d'
{
  "name": "SQL and Databases",
  "instructor": "Vitthal Srinivasan",
  "hours": "15",
  "lectures": "66",
  "certification": "no",
  "quizzes": "no",
  "reviews": ["Based on the MySQL database, I was looking for a more advanced course"]
}
'

curl -XPOST 'localhost:9200/courses/web?pretty' -d'
{
  "name": "jQuery",
  "instructor": "Loonycorn",
  "hours": "9",
  "lectures": "52",
  "certification": "no",
  "reviews": ["Very accessible to beginners"]
}
'

curl -XGET 'localhost:9200/_cat/indices?v&pretty'



Demo 4 - Fetching whole and partial documents

curl -XGET 'localhost:9200/courses/1?pretty'
curl -XGET 'localhost:9200/courses/programming/1?pretty'

curl -XGET 'localhost:9200/courses/programming/10?pretty'

Partial documents

curl -XGET 'localhost:9200/courses/web/1?pretty&_source=false'

curl -XGET 'localhost:9200/courses/web/1?pretty&_source=name,reviews'
curl -XGET 'localhost:9200/courses/web/1?pretty&_source=name,reviews,hours'

curl -XGET 'localhost:9200/courses/programming/1?pretty&_source=name,instructor,hours'

Demo 5 - Updating whole and partial documents

curl -XGET 'localhost:9200/courses/web/3?pretty'


curl -XPUT 'localhost:9200/courses/web/3?pretty' -d'
{
  "name": "PHP",
  "instructor": "Loonycorn",
  "hours": "14",
  "lectures": "75",
  "certification": "no",
  "reviews": ["Love the explanations and the detail", "Very slow moving"]
}
'

Updates using the _update API with "doc"

curl -XGET 'localhost:9200/courses/web/2?pretty'

curl -XPOST 'localhost:9200/courses/web/2/_update?pretty' -d'
{
  "doc": {
     "codelabs": "yes"
  }
}
'

curl -XGET 'localhost:9200/courses/web/2?pretty'

curl -XPOST 'localhost:9200/courses/web/2/_update?pretty' -d'
{
  "doc": {
     "reviews": ["For angular 1.2, would like the latest version",  "Love the examples", "Would have liked it to be more advanced"],
     "completion_certificate": "yes"
  }
}
'

Updates using the _update API with "script"

curl -XPUT 'localhost:9200/courses/math/1?pretty' -d'
{
  "name": "Linear Regression",
  "hours": 4,
  "lectures": 40
}
'

curl -XPUT 'localhost:9200/courses/math/2?pretty' -d'
{
  "name": "Optimization",
  "hours": 2,
  "lectures": 23
}
'

curl -XGET 'localhost:9200/courses/math/1?pretty'
curl -XPOST 'localhost:9200/courses/math/1/_update?pretty' -d'
{
  "script": "ctx._source.lectures += 2"
}
'
curl -XGET 'localhost:9200/courses/math/1?pretty'


curl -XGET 'localhost:9200/courses/math/2?pretty'
curl -XPOST 'localhost:9200/courses/math/2/_update?pretty' -d'
{
  "script": "ctx._source.hours -= 1"
}
'
curl -XGET 'localhost:9200/courses/math/2?pretty'


Demo 6 - Deleting an index 

curl -XDELETE 'localhost:9200/courses/web/2?pretty'
curl -XGET 'localhost:9200/courses/web/2?pretty'

curl -i -XHEAD 'localhost:9200/courses/web/2?pretty'

curl -i -XHEAD 'localhost:9200/courses/web/1?pretty'

curl -XGET 'localhost:9200/_cat/indices?v&pretty'
curl -XDELETE 'localhost:9200/students?pretty'
curl -XGET 'localhost:9200/_cat/indices?v&pretty'


Demo 7 - Bulk indexing documents

Multi-get

curl -XGET 'localhost:9200/_mget?pretty' -d'
{
    "docs" : [
        {
            "_index" : "courses",
            "_type" : "programming",
            "_id" : "1"
        },
        {
            "_index" : "courses",
            "_type" : "programming",
            "_id" : "2"
        }
    ]
}
'

curl -XGET 'localhost:9200/courses/_mget?pretty' -d'
{
    "docs" : [
        {
            "_type" : "programming",
            "_id" : "1"
        },
        {
            "_type" : "programming",
            "_id" : "2"
        }
    ]
}
'

curl -XGET 'localhost:9200/courses/programming/_mget?pretty' -d'
{
    "docs" : [
        {
            "_id" : "1"
        },
        {
            "_id" : "2"
        }
    ]
}
'

Index multiple documents

curl -XPOST 'localhost:9200/_bulk?pretty' -d'
{ "index" : { "_index" : "courses", "_type" : "math", "_id" : "3" } }
{ "name": "Statistics","hours": 3,"lectures": 12 }
{ "index" : { "_index" : "courses", "_type" : "math", "_id" : "4" } }
{ "name": "Calculus","hours": 8,"lectures": 77 }
'

curl -XPOST 'localhost:9200/courses/_bulk?pretty' -d'
{ "index" : {"_type" : "math", "_id" : "3" } }
{ "name": "Statistics","hours": 3,"lectures": 12 }
{ "index" : {"_type" : "math", "_id" : "4" } }
{ "name": "Calculus","hours": 8,"lectures": 77 }
'

curl -XPOST 'localhost:9200/courses/math/_bulk?pretty' -d'
{ "index" : {"_id" : "3" } }
{ "name": "Statistics","hours": 3,"lectures": 12 }
{ "index" : {"_id" : "4" } }
{ "name": "Calculus","hours": 8,"lectures": 77 }
'

Auto-generate ids
curl -XPOST 'localhost:9200/courses/math/_bulk?pretty' -d'
{ "index" : {} }
{ "name": "Statistics","hours": 3,"lectures": 12 }
{ "index" : {} }
{ "name": "Calculus","hours": 8,"lectures": 77 }
'


Bulk operations in one go (paste these one operation at a time)

curl -XPOST 'localhost:9200/courses/math/_bulk?pretty' -H 'Content-Type: application/json' -d'
{ "index" : {"_id" : "3" } }
{ "name": "Statistics","hours": 3,"lectures": 12 }
{ "index" : {"_id" : "4" } }
{ "name": "Calculus","hours": 8,"lectures": 77 }
{ "delete" : {"_id" : "2" } }
{ "create" : {"_id" : "5" } }
{ "name": "Polynomials","hours": 4,"lectures": 44 }
{ "update" : {"_id" : "1"} }
{ "doc" : {"instructor" : "Vitthal Srinivasan"} }
'

Demo 8 - Bulk indexing documents from a JSON file

nano students.json

curl -H "Content-Type: application/x-ndjson" -XPOST 'localhost:9200/students/personal/_bulk?pretty&refresh' --data-binary @"students.json"

curl -XGET 'localhost:9200/_cat/indices?v&pretty'


Module 3

Demo 1 - Create some fake data so we can perform searches

Go to: http://www.json-generator.com/

[
  '{{repeat(1000, 1000)}}',
  {
    name: '{{firstName()}} {{surname()}}',
    age: '{{integer(18, 75)}}',
    gender: '{{gender()}}',
    email: '{{email()}}',
    company: '{{company().toUpperCase()}}',
    phone: '+1 {{phone()}}',
    street: '{{integer(100, 999)}} {{street()}}',
    city: '{{city()}}',
    state: '{{state()}}, {{integer(100, 10000)}}'
  }
]

Make compact

Download and save as students_full.json

Open students_full.json in sublimetext

- Remove the array brackets
- Find-Replace },{ with }\n{ in the regex mode on sublime text
- Find-Replace {"name" with {"index" : {}}\n{"name" in the regex model on sublime text

Now the file is in a format that can be parsed by elastic search

curl -XGET 'localhost:9200/_cat/indices?v&pretty'
curl -XDELETE 'localhost:9200/customers?pretty'
curl -XGET 'localhost:9200/_cat/indices?v&pretty'

Re-create the students index 
curl -H "Content-Type: application/x-ndjson" -XPOST 'localhost:9200/students/personal/_bulk?pretty&refresh' --data-binary @"students_full.json"

curl -XGET 'localhost:9200/_cat/indices?v&pretty'


Demo 2: Searching using the query parameter

curl -XGET 'localhost:9200/students/_search?q=montana&pretty'

localhost:9200/students/_search?q=montana&pretty

localhost:9200/students/_search?q=montana&sort=age:desc&pretty

localhost:9200/students/_search?q=state:kansas&sort=age:asc&pretty

localhost:9200/students/_search?q=state:kansas&from=10&size=2&pretty

localhost:9200/students/_search?q=state:kansas&explain&pretty

Demo 3- Searching using the request body

curl -XGET 'localhost:9200/courses/_search?pretty' -d'
{
  "query": { "match_all": {} }
}
'

curl -XGET 'localhost:9200/courses/_search?pretty' -d'
{
  "query": {}
}
'

curl -XGET 'localhost:9200/courses/_search?pretty' -d'
{
  "query": { "match_all": {} },
  "size": 3
}
'

curl -XGET 'localhost:9200/courses/_search?pretty' -d'
{
  "query": { "match_all": {} },
  "from": 5, 
  "size": 3
}
'
curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
  "query": { "match_all": {} },
  "sort": { "age": { "order": "desc" } },
  "size": 7
}
'

Demo 4 - Query terms and source filtering

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query" : {
        "term" : { "name" : "smith" }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query" : {
        "term" : { "street" : "nolans" }
    }
}
'

Source filtering
curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "_source" : false,
    "query" : {
        "term" : { "street" : "nolans" }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "_source" : "st*",
    "query" : {
        "term" : { "state" : "virginia" }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "_source" : ["st*", "*m*"],
    "query" : {
        "term" : { "state" : "virginia" }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
     "_source": {
        "includes": ["st*", "*m*"],
        "excludes": [ "*il" ]
     },
    "query" : {
        "term" : { "state" : "washington" }
    }
}
'

Demo 5 - Full text queries

The match keyword

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match" : {
            "name" : "rivas"
        }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match" : {
              "name" : {
                  "query" : "durham bray",
                  "operator" : "or"
               }        
        }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match" : {
            "street" : "haring place"
        }
    }
}
'

The match_phrase keyword

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match_phrase" : {
            "street" : "haring place"
        }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match_phrase" : {
            "street" : "haring street"
        }
    }
}
'


curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match_phrase" : {
            "state" : "south dakota"
        }
    }
}
'
The match_phrase_prefix

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match_phrase_prefix" : {
            "name" : "se"
        }
    }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
    "query": {
        "match_phrase_prefix" : {
            "street" : "monroe st"
        }
    }
}
'

Demo 6 - Common terms queries

curl -XGET 'localhost:9200/courses/_search?pretty' -d'
{
    "query": {
        "common": {
            "reviews": {
                "query": "this is great",
                 "cutoff_frequency": 0.001
            }
        }
    }
}
'

Demo 7 - Boolean compound queries

must
curl -XGET 'localhost:9200/students/_search?pretty'  -d'
{
  "query": {
    "bool": {
      "must": [
        { "match": { "street": "roder" } },
        { "match": { "street": "avenue" } }
      ]
    }
  }
}
'
should
curl -XGET 'localhost:9200/students/_search?pretty'  -d'
{
  "query": {
    "bool": {
      "should": [
        { "match": { "street": "roder" } },
        { "match": { "street": "lane" } }
      ]
    }
  }
}
'

must_not
curl -XGET 'localhost:9200/students/_search?pretty'  -d'
{
  "query": {
    "bool": {
      "must_not": [
        { "match": { "state": "arizona kentucky" } },
        { "match": { "street": "avenue street place lane" } }
      ]
    }
  }
}
'

Demo 8 - Term queries

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
  "query": {
    "bool": {
      "should": [
        {
          "term": {
            "state": {
              "value": "delaware"
            }
          }
        },
        {
          "term": {
            "state": {
              "value": "texas"
            }
          }
        }
      ]
    }
  }
}
'

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
  "query": {
    "bool": {
      "should": [
        {
          "term": {
            "state": {
              "value": "delaware",
              "boost": 2.0
            }
          }
        },
        {
          "term": {
            "state": {
              "value": "texas"
            }
          }
        }
      ]
    }
  }
}
'

Demo 9 - Prefixes, Wildcards, Regular expressions

# Note that the name of the index is not specified, this will do a prefix search across all indices

curl -XGET 'localhost:9200/_search?pretty' -d'
{ "query": {
    "prefix" : { "name" : "mon" }
  }
}
'

# * matches any character sequence. ? matches a single character
# Wildcards can be slow so make sure you do not start the search with a * or a ?
# Specifying a prefix before the wildcard expression will help speed up searches

curl -XGET 'localhost:9200/_search?pretty' -d'
{
    "query": {
        "wildcard" : { "state" : "new*" }
    }
}
'

The performance of a regexp query heavily depends on the regular expression chosen. Matching everything like .* is very slow as well as using lookaround regular expressions. If possible, you should try to use a long prefix before your regular expression starts. Wildcard matchers like .*?+ will mostly lower performance.

curl -XGET 'localhost:9200/_search?pretty' -d'
{
    "query": {
        "regexp":{
            "name": "ch.*y"
        }
    }
}
'


Demo 10 - Filters

curl -XGET 'localhost:9200/students/_search?pretty' -d'
{
  "query": {
    "bool": {
      "must": { "match_all": {} },
      "filter": {
        "range": {
          "age": {
            "gte": 25,
            "lte": 35
          }
        }
      }
    }
  }
}
'

Using filters along with search terms

curl -XGET 'localhost:9200/students/_search?pretty' -H 'Content-Type: application/json' -d'
{
  "query": { 
    "bool": { 
      "must": 
        { "match": { 
             "state":   "kentucky"
        }
      },
      "filter": [ 
        { "term":  { "gender": "male" }}, 
        { "range": { "age": { "gte": "50" }}} 
      ]
    }
  }
}
'



Module 4

Demo 1 - Metrics aggregations

Average
curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
    "aggs" : {
        "avg_age" : { 
             "avg" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
    "aggregations" : {
        "avg_age" : { 
             "avg" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 1,
    "aggs" : {
        "avg_age" : { 
             "avg" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

Average with some search terms

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
    "size" : 0,
     "query" : {
          "bool" : {
               "filter" : {
                   "match" : { "state" : "wyoming" }
               }
           }
     },
    "aggs" : {
        "avg_age" : { 
             "avg" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

Stats

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
    "size" : 0,
    "aggs" : {
        "age_stats" : { 
             "stats" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

Demo 2 - Aggregations might need fielddata, e.g. cardinality aggregation
Cardinality

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
    "aggs" : {
        "age_count" : { 
             "cardinality" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
    "aggs" : {
        "gender_count" : { 
             "cardinality" : { 
                 "field" : "company" 
             } 
         }
    }
}
'

curl -XPUT 'localhost:9200/students/_mapping/personal?pretty' -d'
{
  "properties": {
    "company": { 
      "type":     "text",
      "fielddata": true
    }                              
  }            
}         
'

Now re-run the original request
curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
    "aggs" : {
        "gender_count" : { 
             "cardinality" : { 
                 "field" : "company" 
             } 
         }
    }
}
'

Demo 3 - Bucketing aggregation by field values

Term aggregations
curl -XPUT 'localhost:9200/students/_mapping/personal?pretty' -d'
{
  "properties": {
    "gender": { 
      "type":     "text",
      "fielddata": true
    }                              
  }            
}         
'

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
        "gender_bucket" : { 
             "terms" : { 
                 "field" : "gender" 
             } 
         }
    }
}
'
curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
        "age_bucket" : { 
             "terms" : { 
                 "field" : "age" 
             } 
         }
    }
}
'

Range aggregation

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
       "age_ranges" : {
           "range" : {
               "field" : "age",
               "ranges" : [
                   { "to" : 35 },
                   { "from" : 36, "to" : 50 },
                   { "from" : 50 }
                ]
            }
        }
     } 
}
'

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
       "age_ranges" : {
           "range" : {
               "field" : "age",
               "keyed" : true,
               "ranges" : [
                   { "to" : 35 },
                   { "from" : 36, "to" : 50 },
                   { "from" : 50 }
                ]
            }
        }
     } 
}
'

curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
       "age_ranges" : {
           "range" : {
               "field" : "age",
               "keyed" : true,
               "ranges" : [
                   { "key": "young", "to" : 365 },
                   { "key": "middle-aged", "from" : 36, "to" : 50 },
                   { "key": "senior", "from" : 50 }
                ]
            }
        }
     } 
}
'

Demo 4 - Nesting aggregations

2 level nesting
curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
        "gender_bucket" : { 
             "terms" : { 
                 "field" : "gender" 
             }, 
             "aggs": {
                 "average_age": {
                      "avg": {
                          "field": "age"
                      }
                 }
              }
         }
    }
}
'

3 level nesting
curl -XPOST 'localhost:9200/students/_search?&pretty' -d'
{
   "size" : 0,
   "aggs" : {
        "gender_bucket" : { 
             "terms" : { 
                 "field" : "gender" 
             }, 
             "aggs" : {
                 "age_ranges" : {
                     "range" : {
                         "field" : "age",
                         "keyed" : true,
                         "ranges" : [
                             { "key": "young", "to" : 30 },
                             { "key": "middle-aged", "from" : 30, "to" : 55 },
                             { "key": "senior", "from" : 55 }
                          ]
                      },
                      "aggs": {
                          "average_age": {
                               "avg": {
                                   "field": "age"
                               }
                          }
                       }
                  }
               } 
         }
    }
}
'

Demo 5 - Filter and filters aggregations

curl -XPOST 'localhost:9200/students/_search?size=0&pretty' -d'
{
    "aggs" : {
        "state" : {
            "filter" : { "term": { "state": "vermont" } },
            "aggs" : {
                "avg_age" : { "avg" : { "field" : "age" } }
            }
        }
    }
}
'

Filters

curl -XGET 'localhost:9200/students/_search?pretty'  -d'
{
  "size": 0,
  "aggs" : {
    "states" : {
      "filters" : {
        "filters" : {
          "alabama" :   { "match" : { "state" : "alabama"   }},
          "north dakota" :   { "match" : { "state" : "north dakota"   }},
          "south carolina" : { "match" : { "state" : "south carolina" }}
        }
      }
    }
  }
}
'

(Anonymous filters, returned in the same order as the original filter specification)
curl -XGET 'localhost:9200/students/_search?pretty'  -d'
{
  "size": 0,
  "aggs" : {
    "states" : {
      "filters" : {
        "filters" : [
          { "match" : { "state" : "alabama"   }},
          { "match" : { "state" : "north dakota"   }},
          { "match" : { "state" : "south carolina" }}
        ]
      }
    }
  }
}
'

Other bucket
curl -XGET 'localhost:9200/students/_search?pretty'  -d'
{
  "size": 0,
  "aggs" : {
    "states" : {
      "filters" : {
        "other_bucket_key": "other_states",  
        "filters" : {
          "washington" :   { "match" : { "state" : "alabama"   }},
          "north carolina" :   { "match" : { "state" : "north dakota"   }},
          "south dakota" : { "match" : { "state" : "south carolina" }}
        }
      }
    }
  }
}
'


Module 5

Demo 1 - Running commands in the Python REPL

Elastic search in Python

pip install elasticsearch

(For Python 3)
pip3 install elasticsearch


All the API calls map the raw REST api as closely as possible, including the distinction between required and optional arguments to the calls. This means that the code makes distinction between positional and keyword arguments; we, however, recommend that people use keyword arguments for all calls for consistency and safety.


First cluster wide APIs: https://elasticsearch-py.readthedocs.io/en/master/api.html#cluster


python


from elasticsearch import Elasticsearch

es = Elasticsearch(['localhost:9200'])
print es.cluster.health()

import json

def print_json(j):
   print_json(j)

health = es.cluster.health(index="students", level="cluster")

print_json(health)

print_json(es.cluster.stats())

print_json(es.cluster.state())


Demo 2 - Python commands dealing with indices

APIs to deal with indices: https://elasticsearch-py.readthedocs.io/en/master/api.html#indices


# An API call is considered successful (and will return a response)
# if elasticsearch returns a 2XX response.
es.indices.create(index='enrolled')

# This will throw an error as the index is already created
es.indices.create(index='enrolled')

# Ignore those errors
es.indices.create(index='enrolled', ignore=400)

es.indices.exists(index='students')

es.indices.exists(index='studentsss')

print_json(es.indices.get(index="students"))

es.indices.validate_query(index="students", body='{ "query": {"prefix" : { "name" : "do" }}}')

es.indices.validate_query(index="students", body='{ "query": { "match_phrase" : {"state" : "* dakota"}}}')


# This one is not valid
es.indices.validate_query(index="students", body='{ "query": { "match_blah" : {"state" : "* dakota"}}}')


es.indices.delete(index='enrolled', ignore=[400, 404])


Demo 3 - Working with documents using Python APIs

es.create(index="courses", doc_type="programming", id="23", body='{"name": "Scala","instructor": "Vitthal Srinivasan", "hours": 7}')

es.create(index="courses", doc_type="programming", id="24", body='{"name": "Java","instructor": "Loonycorn", "hours": 17}')

es.create(index="courses", doc_type="programming", id="25", body='{"name": "Python","instructor": "Loonycorn", "hours": 8}')


print_json(es.get(index="courses", doc_type="programming", id="23"))

print_json(es.get(index="courses", doc_type="programming", id="23", _source="False"))

print_json(es.get(index="courses", doc_type="programming", id="23", _source_include="name"))

print_json(es.get(index="courses", doc_type="programming", id="23", _source_exclude="name"))


print_json(es.delete(index="courses", doc_type="programming", id="23"))


es.delete_by_query(index="_all", body='{"query": {"match" : {"name" : "john"}}}')



Demo 4 - Search and aggregations using the Python API
https://elasticsearch-py.readthedocs.io/en/master/api.html#elasticsearch

es.search(index="students")

es.search(index="students", body='{"query": {"match_phrase_prefix" : {"street" : "monroe st"}}}')


# Counts all documents in this index, equivalent of a match_all
es.count(index="students")

es.count(index="courses")

# Counts all documents in this index of this type
es.count(index="courses", doc_type="math")

# Counts the documents which match the search query
es.count(index="students", doc_type="math", body='{"query": {"match" : {"name" : "rivas"}}}')


Module 6 - Visualizations with Kibana

Make notes from here
https://www.elastic.co/products/kibana
https://www.elastic.co/guide/en/kibana/current/getting-started.html

Download from here
https://www.elastic.co/downloads/kibana


Load the data for visualization from here
https://www.elastic.co/guide/en/kibana/current/tutorial-load-dataset.html

unzip accounts.zip
ls -l
Show accounts.json

gunzip logs.jsonl.gz
ls -l
Show logs.jsonl


Specify mappings for the Shakespeare index.

Mapping is the process of defining how a document, and the fields it contains, are stored and indexed. For instance, use mappings to define:
	•	which string fields should be treated as full text fields.
	•	which fields contain numbers, dates, or geolocations.
	•	whether the values of all fields in the document should be indexed into the catch-all _allfield.
	•	the format of date values.
	•	custom rules to control the mapping for dynamically added fields.

https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html


Format of each kind of data here: https://www.elastic.co/guide/en/kibana/current/tutorial-load-dataset.html


curl -XPUT 'localhost:9200/shakespeare?pretty' -H 'Content-Type: application/json' -d'
{
 "mappings" : {
  "_default_" : {
   "properties" : {
    "speaker" : {"type": "keyword" },
    "play_name" : {"type": "keyword" },
    "line_id" : { "type" : "integer" },
    "speech_number" : { "type" : "integer" }
   }
  }
 }
}
'

	•	Because the speaker and play_name fields are keyword fields, they are not analyzed. The strings are treated as a single unit even if they contain multiple words.
	•	The line_id and speech_number fields are integers.


Log data has 

https://www.elastic.co/guide/en/elasticsearch/reference/current/geo-point.html

Geo point data are basically lat long pairs that can be used for including distance as a relevant factor in search

	•	to find geo-points within a bounding box, within a certain distance of a central point, or within a polygon.
	•	to aggregate documents by geographically or by distance from a central point.
	•	to integrate distance into a document’s relevance score.
	•	to sort documents by distance.


curl -XPUT 'localhost:9200/logstash-2015.05.18?pretty' -H 'Content-Type: application/json' -d'
{
  "mappings": {
    "log": {
      "properties": {
        "geo": {
          "properties": {
            "coordinates": {
              "type": "geo_point"
            }
          }
        }
      }
    }
  }
}
'

curl -XPUT 'localhost:9200/logstash-2015.05.19?pretty' -H 'Content-Type: application/json' -d'
{
  "mappings": {
    "log": {
      "properties": {
        "geo": {
          "properties": {
            "coordinates": {
              "type": "geo_point"
            }
          }
        }
      }
    }
  }
}
'

curl -XPUT 'localhost:9200/logstash-2015.05.20?pretty' -H 'Content-Type: application/json' -d'
{
  "mappings": {
    "log": {
      "properties": {
        "geo": {
          "properties": {
            "coordinates": {
              "type": "geo_point"
            }
          }
        }
      }
    }
  }
}
'

Bulk index these documents

curl -H 'Content-Type: application/x-ndjson' -XPOST 'localhost:9200/bank/account/_bulk?pretty' --data-binary @accounts.json
curl -H 'Content-Type: application/x-ndjson' -XPOST 'localhost:9200/shakespeare/_bulk?pretty' --data-binary @shakespeare.json
curl -H 'Content-Type: application/x-ndjson' -XPOST 'localhost:9200/_bulk?pretty' --data-binary @logs.jsonl



Define index patterns

We use index patterns to find and visualize our indices in Kibana

https://www.elastic.co/guide/en/kibana/current/tutorial-define-index.html

























