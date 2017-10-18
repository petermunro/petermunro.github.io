# Using Pipes

## Pipe Practice

1. Display today's date in ISO-8601 format (eg `2017-10-02`).
2. This value has been provided as the result of a foreign exchange conversion:
   `129.26913`. Display it as a USD currency value, but with a maximum of
   2 digits after the decimal point. Does rounding occur?
3. How would you use the `SlicePipe` to display the first 5 elements of a list?
   Try it.
4. Lookup the documentation for the `JsonPipe`.
   Create a component which displays the `event` object for a mouse click as JSON in your web page.


## Writing a Custom Pipe

TODO:

We don't want to use a pipe to filter the LH pane, as that will filter the content from the server.
So we need a pipe to filter something else.
The RH pane could be a candidate. We  could filter entries added for a given object view (eg music track or mammal etc).

1. Create a custom pipe which
