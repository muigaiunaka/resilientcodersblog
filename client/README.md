## Accessing from the Front End

### React
1) Create a file called sanity.js (if using create-react-app, create a folder called *utils* in /src folder. Result: /src/utils/sanity.js) and copy the content below into it.
```
const sanityClient = require('@sanity/client')
export default sanityClient({
    // Find your project ID and dataset in `sanity.json` in your studio project
    projectId: (process.env.NODE_ENV === "production" ? '' : 'o4iq4xmw'), // different id based off of envi
    dataset: (process.env.NODE_ENV === "production" ? 'production' : 'development'), // different data sets based off of envi
    useCdn: true
    // useCdn == true gives fast, cheap responses using a globally distributed cache.
    // Set this to false if your application require the freshest possible
    // data always (potentially slightly slower and a bit more expensive).
}) 
```

2. In component, import sanity
```
import React from 'react';
import sanity from './sanity';
```
3. Create a graphql query for posts
```
const query = `*[_type == "post"] {title, 'mainImage': mainImage.asset->url, _id, slug}`;
```
and fetch the data returned in the query before the component mounts
```
    componentDidMount() {
        sanity.fetch(query).then(posts => {
            this.setState({ posts: posts })
        })
    }
```
After this you should have access to all of the posts in the posts property of state

Cheers :D