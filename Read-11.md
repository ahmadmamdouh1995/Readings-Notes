## This request has a single required parameter:

q - Search for volumes that contain this text string. There are special keywords you can specify in the search terms to search in particular fields, such as:
intitle: Returns results where the text following this keyword is found in the title.
inauthor: Returns results where the text following this keyword is found in the author.
inpublisher: Returns results where the text following this keyword is found in the publisher.
subject: Returns results where the text following this keyword is listed in the category list of the volume.
isbn: Returns results where the text following this keyword is the ISBN number.
lccn: Returns results where the text following this keyword is the Library of Congress Control Number.
oclc: Returns results where the text following this keyword is the Online Computer Library Center number.

## Optional query parameters
In addition to the standard query parameters, you can use the following query parameters when performing a volumes search.

Download Format
You use the download parameter to restrict the returned results to volumes that have an available download format of epub by setting the to the value epub.

The following example searches for books with an epub download available:GET https://www.googleapis.com/books/v1/volumes?q=pride+prejudice&download=epub&key=yourAPIKey

## Filtering
You can use the filter parameter to restrict the returned results further by setting it the to one of the following values:

partial - Returns results where at least parts of the text are previewable.
full - Only returns results where all of the text is viewable.
free-ebooks - Only returns results that are free Google eBooks.
paid-ebooks - Only returns results that are Google eBooks with a price.
ebooks - Only returns results that are Google eBooks, paid or free. Examples of non-eBooks would be publisher content that is available in limited preview and not for sale, or magazines.
The following example restricts search results to those available as free eBooks:

GET https://www.googleapis.com/books/v1/volumes?q=flowers&filter=free-ebooks&key=yourAPIKey

## Pagination
You can paginate the volumes list by specifying two values in the parameters for the request:

startIndex - The position in the collection at which to start. The index of the first item is 0.
maxResults - The maximum number of results to return. The default is 10, and the maximum allowable value is 40.
Print Type
You can use the printType parameter to restrict the returned results to a specific print or publication type by setting it to one of the following values:

all - Does not restrict by print type (default).
books - Returns only results that are books.
magazines - Returns results that are magazines.
The following example restricts search results to magazines:

GET https://www.googleapis.com/books/v1/volumes?q=time&printType=magazines&key=yourAPIKey

## Projection
You can use the projection parameter with one of the following values to specify a predefined set of Volume fields to return:

full - Returns all Volume fields.
lite - Returns only certain fields. See field descriptions marked with double asterisks in the Volume reference to find out which fields are included.
The following example returns search results with limited volume information:

GET https://www.googleapis.com/books/v1/volumes?q=flowers&projection=lite&key=yourAPIKey

## Sorting
By default, a volumes search request returns maxResults results, where maxResults is the parameter used in pagination (above), ordered by relevance to search terms.

You can change the ordering by setting the orderBy parameter to be one of these values:

relevance - Returns results in order of the relevance of search terms (this is the default).
newest - Returns results in order of most recently to least recently published.
The following example lists results by published date, newest to oldest:

GET https://www.googleapis.com/books/v1/volumes?q=flowers&orderBy=newest&key=yourAPIKey


## Retrieving a specific volume
You can retrieve information for a specific volume by sending an HTTP GET request to the Volume resource URI:

https://www.googleapis.com/books/v1/volumes/volumeId

## Request
Here is an example of a GET request that gets a single volume:

GET https://www.googleapis.com/books/v1/volumes/zyTCAlFPjgYC?key=yourAPIKey

## Response
If the request succeeds, the server responds with the 200 OK HTTP status code and the Volume resource requested:

200 OK

## Working with bookshelves in "My Library"
All "My Library" requests apply to the authenticated user's data.

Retrieving a list of my bookshelves
You can retrieve a listing of all of the authenticated user's bookshelves by sending an HTTP GET request to the URI with the following format:

https://www.googleapis.com/books/v1/mylibrary/bookshelves

## Optional query parameters
You can use the standard query parameters when retrieving the list of the authenticated user's bookshelves.

Retrieving a list of volumes on my bookshelf
You can retrieve a listing of the volumes on the authenticated user's bookshelf by sending an HTTP GET request to the URI with the following format:

https://www.googleapis.com/books/v1/mylibrary/bookshelves/shelf/volumes

Replace the shelf path parameter with the ID of the bookshelf. See the Google Books IDs section for more information on bookshelf IDs.

## Query parameter reference
The query parameters you can use with the Books API are summarized in this section.  All parameter values need to be URL encoded.

Standard query parameters
Query parameters that apply to all Books API operations are shown in the table below.

Notes (on API keys and auth tokens):

The key parameter is required with every request, unless you provide an OAuth 2.0 token with the request.
You must send an authorization token with every request that requires an OAuth scope. OAuth 2.0 is the only supported authorization protocol.
You can provide an OAuth 2.0 token with any request in one of two ways:
Using the access_token query parameter like this: ?access_token=oauth2-token
Using the HTTP Authorization header like this: Authorization: Bearer oauth2-token
All parameters are optional except where noted.

