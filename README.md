**Nadya Aysha [2206081635] ProLan B**

# Modul 6

### Commit (1) Reflection Notes  

In this milestone, I've built a simple single-threaded web server using Rust’s `std::net::TcpListener` and `TcpStream`. Initially, the server only accepted incoming connections,
but after implementing the `handle_connection` function, I was able to read and display HTTP requests from a browser. By using `BufReader` and `.lines()`, request lines were collected
until we encountered an empty line, indicating the end of the HTTP request header. This exercise helped me understand how a browser communicates with a server via HTTP,
providing insight into how requests are structured and processed. This was kind of fun! (I hope I'm not speaking too soon, LOL).

### Commit (2) Reflection Notes  

In this milestone, I've modified the `handle_connection` function to return an actual HTML response to the browser. By reading the contents of `hello.html` and formatting a proper HTTP response
with a status line, `Content-Length`, and body, I enabled the server to serve static files. This helped deepen an understanding of how HTTP responses are structured and how browsers interpret them.
Also, I learned the importance of correctly setting response headers to ensure proper rendering. This implementation provides the foundation for serving dynamic content in future steps. I also modified the HTML file
to display my name.

### Commit (3) Reflection Notes  

In this milestone, I've enhanced the server to differentiate between valid and invalid requests by checking the requested path. If the request is for the root (`/`), it will return `hello.html`,
otherwise, it'll return a custom 404 page. I've also refactored the code to separate response construction, making it cleaner and easier to maintain. This step highlighted the importance of structured request handling
and refactoring for better readability and scalability in web server development.

### Commit (4) Reflection Notes  

In this milestone, simulating a slow response showed how a single-threaded server blocks all requests when one takes too long. A `/sleep` request delayed others, highlighting the need for multithreading
or async processing to improve performance and scalability.

### Commit (5) Reflection Notes

In this final milestone, I've implemented ThreadPool to handle multiple client requests concurrently and improve efficiency. The ThreadPool create worker threads that continuously listen for new tasks and execute them asynchronously.
Previously, the server handled requests one at a time, blocking new connections until the current request was processed. Now, multiple requests can be processed at the same time, improving responsiveness.