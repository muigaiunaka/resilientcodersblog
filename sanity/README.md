Sanity CMS

![Sanity](./sanity.png?raw=true)

## Accessing the CMS

1. Clone the project

```
git clone https://github.com/muigaiunaka/resilientcodersblog.git
```
2. Install Sanity Command Line Interface globally

```
npm install -g @sanity/cli
```

3. Running the Studio Editor 
> Note: On Google Chrome, the local Studio Editor for the CMS may not run. Use Firefox to view and edit content
## Running

```
cd resilientcodersblog/sanity
npm install
npm start
```
Locate the CMS running at: http://localhost:3333/

## Development

### Data Schemas Available

<table>
  <tr><td width="300px" colspan="2"><center><b>Author</b></center></td></tr>
  <tr><td>name</td><td>String</td></tr>
  <tr><td>url</td><td>String</td></tr>
  <tr><td>slug</td><td>String</td></tr>
  <tr><td>image</td><td>Image</td></tr>
  <tr><td>block</td><td>Array</td></tr>
</table>

<table>
  <tr><td width="300px" colspan="2"><center><b>Post</b></center></td></tr>
  <tr><td>name</td><td>String</td></tr>
  <tr><td>author</td><td>Author</td></tr>
  <tr><td>slug</td><td>String</td></tr>
  <tr><td>categories</td><td>Category[]</td></tr>
  <tr><td>mainImage</td><td>Image</td></tr>
  <tr><td>publishedAt</td><td>datetime</td></tr>
  <tr><td>body</td><td>blockContent</td></tr>
</table>

<table>
  <tr><td width="300px" colspan="2"><center><b>Category</b></center></td></tr>
  <tr><td>title</td><td>String</td></tr>
  <tr><td>description</td><td>Text</td></tr>
</table>