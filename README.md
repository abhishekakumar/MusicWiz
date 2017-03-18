# MusicWiz
Music touches upon the lives of many people. While there are many applications which allow users to
listen and watch songs and records, there are very few applications which allow efficient searching for
music. Searching music by the name of the song is currently the most common way. But sometimes you
do not know the actual song but know other details about the song like the artist, album, release year, etc.
These additional details about the data is called metadata. In addition to the music content, there are many
metadata associated with a record. The information about the artist, their works and the relationship between
them form a triple and can be stored in RDF data model. Each work can have information like an album
title, track titles, length of each track, release date and country, and additional metadata. This metadata can
be used to find knowledge about the music. Field of music is evolving and new music is being generated
every moment. Thus the relationship between the artist and their works keeps changing. For example, when
an artist launches a new album, the existing relationships need to be updated to reflect this new album. RDF
data model allows to have dynamic relationships.

MusicWiz is a web application which provides users the capability to do complex searches on the music
data like “Which song was composed by Coldplay and performed in the year 2000”, “Artist who composed
‘Hello’ song in the year 2015 and was released in USA”. The answers to these queries are not generated
using table joins as in relational databases or using key word matching as search engines like Google and
Yahoo, but are generated using metadata available in structured RDF form. These kind of queries allow us to have greater knowledge from the data. In addition to searching for music, the application also provides
a dashboard of top artists and trends of albums.

## Architecture
MusicWiz is designed on the three tiered web architecture. Three tiered architecture is a client-server architecture
pattern where the user interface, application rules and data access are separated. Developing the
application in three tiered architecture provides modular design and allows us to separate different layers
of the application to use different technologies. This helps to choose the best technology for the particular
layer and each layer can be updated independently in the future if needed.

### User Interface
MusicWiz is a single page web application that was designed to provide users the capability to do complex
searches on the MusicBrainz database using a simple user interface. The user interface is implemented using AngularJS,
HTML and CSS.

![alt tag](https://github.com/abhishekakumar/MusicWiz/blob/master/WebContent/images/SearchBox.png)

![alt tag](https://github.com/abhishekakumar/MusicWiz/blob/master/WebContent/images/PieChart.png)

![alt tag](https://github.com/abhishekakumar/MusicWiz/blob/master/WebContent/images/BarChart.png)

### Service Layer
The user interface interacts with the data using a set of REST web service endpoints. REST web services used in the application are developed in Java using Jersey framework.The Java code interacts with Jena using java application interfaces provided by Jena. Jena provides application interfaces only in java programming language.

### Database Structure
The music data in RDF format is obtained from LinkedBraiz. LinkedBrainz project publishes MusicBrainz
data in linked data format. MusicBrainz is community supported where metadata about music is
crowd sourced. MusicBrainz provides these data as open source to the community in form of relational data
in PostgreSQL database. LinkedBraiz converted these relational data into RDF data using D2R mappings.
![alt tag](https://github.com/abhishekakumar/MusicWiz/blob/master/WebContent/images/DBdiagram.JPG)

## Free Text Search
The comprehensive search functionality is developed using Jena’s special text search feature. ARQ is
the query engine of Jena. An extension to ARQ combines text search and SPARQL allowing applications
to perform free text searches within SPARQL queries. The text index was built using Apache Lucene. MusicWiz performs indexing using Lucene built inside Jena Fuseki. An index is built upon all the data in the rdf stored in Jena TDB. The text index is additional information along with the RDF data. The SPARQL query first scans the index to find the search string and then returns a reverse mapping to RDF URI triples.
