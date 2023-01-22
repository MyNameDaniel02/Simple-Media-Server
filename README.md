## Welcome to Simple Media Server

The media server is designed to keep track of files and metadata information regarding
various audio and video media. This program was developed for testing flask and SQL.

### Schema Description

![ERD](ISYS2120_a3_erd.png)

As per the above schema you have various consumable media:

1. Movies
1. TV Shows (which have TV Episodes)
1. Songs (which are performed by Artists and appear in Albums)
1. Podcasts (which have Podcast Episodes)

There is also some User Account information which contains information about the user
including:

1. Contact Methods
1. Username / password
1. Subscribed podcasts
1. Consumed media

We have abstracted most of the common elements such descriptions, artwork and genres
into a MetaData table system. The primary Metadata table contains 3 fields:

1. an ID field (which other tables use a FK)
1. a MetaData type ID field (which maps to the MetaDataType table)
1. an actual value for the metadata

Presently, there are 4 possible types of metadata:

1. Song Genre
1. Film Genre
1. Artwork
1. Description

#### Example Functionalities

1. A user logs into the system by providing their username and password. Once logged in, they reach the landing page which displays:

    1. User subscribed Podcasts
    1. User Playlists
    1. User current in-progress items
1. When a user clicks on a song, they should see all the song information, including:

    1. Song Name
    2. Song Artists
    2. Song length
    2. Song Metadata such as Artwork, description, Genres
1. When a user clicks on the ’tv shows’ nav item, they should see a list of all tv shows information, including:
    
    1. TV Show ID
    2. TV Show Name
    2. Total number of tv show episodes for this tv show
1. When a user clicks on a single tv Show, they should see a list of relevant information, including:

    1. TV Show Name
    2. TV Show Metadata such as Artworks, Descriptions, Genres
    2. A list of every episode for this tv show ordered by Season and then Episode including:
        
        1. TV Show Episode ID
        3. TV Show Episode Title
        3. Season
        3. Episode
        3. AirDate
1. When a user clicks on a single Album, they should see a list of relevant information, including:

    1. Album Name
    2. Album Metadata such as Artworks, Descriptions
    2. All genres for this Album. The Genres for an album are composed of all the Genres for all it’s songs.
    2. A list of all songs in an album ordered by track number including:

        1. the song ID
        3. the Song Name
        3. The Song Artist(s)
        
1. When a user clicks on a single podcast from the ’podcasts’ list (or their subscribed podcasts), they should see a list of relevant information including:

    1. Podcast ID
    2. Podcast Name
    2. Podcast URI
    2. Last Updated
    2. Podcast Metadata such as Artworks, Descriptions, Genres
    2. A list of all podcast episodes in this podcast ordered by descending publication date including:

        1. Podcast Episode ID
        3. Podcast Episode Title
        3. Podcast Episode URI
        3. Podcast Episode Date Published
        3. Podcast Episode Length
1. When A user clicks on a single podcast episode from the list in part 7, they should see all relevant podcast episode information including:

    1. Podcast Episode ID
    2. Podcast Episode Title
    2. Podcast Episode URI
    2. Podcast Episode Date Published
    2. Podcast Episode Length
    2. Podcast Episode Metadata such as Artworks, Descriptions, Genres

1. When a user clicks on a single genre, they should see all appropriate items that are associated with that genre (Movies and TV Shows for 'film genre'; Songs for 'song genre'; and Podcasts for 'podcast genre'). Each item listed should include the following:
    
    1. Item ID
    1. Item Title
    1. Item Type (Movie / Tv Show / Song / Podcast)
    
