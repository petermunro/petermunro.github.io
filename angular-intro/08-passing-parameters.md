# Passing Parameters to Components


1. Write a `MessageComponent` that can be invoked like this:

        <message></message>

   or like this:

        <message text=”a test message”></message>

   The component simply displays the message provided by the `text` property, or a suitable default message if none is provided.

2. Include the `MessageComponent` in your app

   Display the component, once using the default message, and once by supplying its text as an attribute.

### Review Quiz

What do these do?
- `<message text=”hello”></message>`
- `<message text=”{{title}}”></message>`
- `<message [text]=”title”></message>`
- `<message [text]=”’title’”></message>`
