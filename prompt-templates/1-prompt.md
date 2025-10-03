Hey, I need your help in improving the flow for [@script.js](/path/to/public/script.js), which will be used in [@index.html](/path/to/public/index.html).

So, I need you to check the [@index.js](/path/to/index.js) file, especially the `/chat` endpoint.

The endpoint flow is like the following:
- The request body has the `conversation` property, which is an array of objects
- This array of objects contain the following properties: `role` and `text`
- There will be several conditions via the following guard clauses:
  - Guard Clause #1: Checks whether the `conversation` is an array of objects or not
  - Guard Clause #2: Checks whether each of the object in the array contains valid conditions
- Then, after both clauses fulfilled, the flow continues with the content mapping, which then be pushed to the Google Gemini AI model, through `generateContent()` function
- After that, the response will contain `{ success: boolean, data: string | null, message: string }`

Now, the flow in the front-end is like this:
- User types the message, and then sends the message
- Then, the [@script.js](/path/to/public/script.js) will catch the event, and then creates request to `POST /chat` on file [@index.js](/path/to/index.js), with an array of object, where the sender (or the user) will act as the `user` (role: `user`)
- Once the request is complete, the response must be pushed into the conversation array as the same as the message structure (`{ role: 'model', text: '<Google Gemini AI model response>' }`)

Can you help me in achieving the above flow?
