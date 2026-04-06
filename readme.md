# Static files server

**Read [the guideline](https://github.com/mate-academy/js_task-guideline/blob/master/README.md) before start**

Create a server that will return files using a part of the path after `/file/`.

## Rules

- Return only files from a folder `public`
- There should not be access to any other files
- Return **404** status for non existent files (with `text/plain` content type)
- If the pathname does not start with `/file/` return a message with a hint how to load files (`text/plain`)
- If the pathname is exactly `/file` return a hint message (`text/plain`)
- If the pathname contains `../` return **400** status
- If the pathname contains duplicated slashes (`//`) return **404** status

## Examples

| Request | Result |
|--------|--------|
| /file/index.html | returns public/index.html |
| /file/styles/main.css | returns public/styles/main.css |
| /file/ | returns public/index.html |
| /file | returns hint message |
| /file/nonexistent.txt | returns 404 |
| /file/../app.js | returns 400 |
| /file//styles//main.css | returns 404 |
| /anything | returns hint message |

## Content-Type

| Type | Content-Type |
|------|--------------|
| .html | text/html |
| .css | text/css |
| errors | text/plain |
| hint | text/plain |
