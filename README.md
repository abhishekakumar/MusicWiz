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
