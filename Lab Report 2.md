```
import java.io.*;
import java.net.*;
import com.sun.net.httpserver.*;

public class StringServer {
    private static String message = "";

    static class MyHandler implements HttpHandler {
        @Override
        public void handle(HttpExchange t) throws IOException {
            String response = "";
            String path = t.getRequestURI().getPath();

            if (path.equals("/add-message")) {
                String query = t.getRequestURI().getQuery();
                String[] params = query.split("=");
                if (params.length == 2 && params[0].equals("s")) {
                    String newMessage = params[1];
                    message += (message.isEmpty() ? "" : "\n") + (message.lines().count() + 1) + ". " + newMessage;
                    response = message;
                }
            }

            t.sendResponseHeaders(200, response.length());
            OutputStream os = t.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }

    public static void main(String[] args) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(8000), 0);
        server.createContext("/", new MyHandler());
        server.setExecutor(null); // creates a default executor
        server.start();
    }
}
```

 ![Image](2-1.png)

 ![Image](2-2.png)