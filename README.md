# Destroy all libraries
Libraries are great, lets reduce the amount we have.

## Reason

I was tinkering around with NodeJS and running sub processes using the `spawn` method from NodeJS. I wanted to protect myself from, well, myself and escape the data is send to the method. Searching for it made me run into [this](https://github.com/nodejs/node/issues/29532) issue in the NodeJS repository, where they are talking about implement argument escaping to NodeJS itself. 

The next thing I ran into was the [shell-quote](https://www.npmjs.com/package/shell-quote) library, that does exactly what I wanted. To my horror I saw it being downloaded 25 million times a week, though a small library, it still racks up ~500GB of weekly data. 

If we could include the functionality  of the `shell-quote` library into NodeJS we could reduce the amount of data send over the web, it should not be a ~500GB a week reduction as NodeJS will become larger, but my asumption is that it's generally not redownloaded as often as libraries.

## The List

This is the list of libraries / functionality that I believe should be part of the NodeJS run time. 

- [shell-quote](https://www.npmjs.com/package/shell-quote) - escaping shell arguments, enable using a option for backwards compatibility. Made default during a major release?
- https://github.com/purposeindustries/window-or-global
