# lab 2

## PART 1

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class Handler implements URLHandler {

    List<String> messages = new ArrayList<>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("This is ChatServer");
        } else {
            if (url.getPath().contains("/add-message")) {
                String urlString = url.toString();
                String message = "";
                String user = "";

                if (url.getQuery().contains("s=")) {
                    message = urlString.split("s=")[1];
                    message = message.split("&")[0];
                }

                if (url.getQuery().contains("user=")) {
                    user = urlString.split("user=")[1];
                }

                String newMessage = String.format("%s: %s", user, message);
                messages.add(newMessage);

                // Combine all messages and separate them with newlines
                return String.join("\n", messages);
            }
            return "404 Not Found!";
        }
    }
}

class NumberServer {
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

## First screenshot

<img width="486" alt="Screenshot 2024-01-30 at 12 58 27 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/3d780de0-7e01-4e39-ba81-924dcc7edcff">

The method `handleRequest` is called. This method takes in the url, which in this case is `http://localhost:4000/add-message?s=hi&user=ari`. 
The values of the string variables `urlString`, `user`, and `message` get changed. `urlString` gets changed to the current url, which is passed into the method `handleRequest`. 
The variable `user` gets changed to whatever is in front of the `user=` portion of the url -- in this case, `user = "ari"`. 
The variable `message` gets changed to whatever is in front of the `s=` portion of the url -- in this case, `message = "hi"`. 
Then, the string `newMessage` takes in the user and the message and formats them.
The `StringBuilder message` field gets updated since there is new message info.

## Second screenshot

<img width="504" alt="Screenshot 2024-01-30 at 12 58 50 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/8e32f2e5-78dc-4637-814e-1df5cc7d336f">

The method `handleRequest` is called. This method takes in the url, which in this case is `http://localhost:4000/add-message?s=bye&user=joe`. 
The values of the string variables `urlString`, `user`, and `message` get changed. `urlString` gets changed to the current url, which is passed into the method `handleRequest`. 
The variable `user` gets changed to whatever is in front of the `user=` portion of the url -- in this case, `user = "joe"`. 
The variable `message` gets changed to whatever is in front of the `s=` portion of the url -- in this case, `message = "bye"`. 
Then, the string `newMessage` takes in the user and the message and formats them. The new line is added below the previous one. 
No values get changed since the query is invalid.

## PART 2

Private key:

<img width="570" alt="Screenshot 2024-01-30 at 1 14 24 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/26024360-79f5-4fe7-926e-63d0f6827b8c">
(Note for grader: I fixed exerything else in my lab report, but I was unable to update the screenshots because my old laptop broke and everything I worked on (including the public and private key) was on there. I hope this will not negatively impact this lab report.)

Public key:

<img width="567" alt="Screenshot 2024-01-30 at 1 13 42 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/ff19db24-11ae-427e-9ac7-39b437c90482">

Login without password:

<img width="565" alt="Screenshot 2024-01-30 at 1 38 59 PM" src="https://github.com/aaj005/cse15l-lab-reports/assets/156254216/d7aef372-9702-4356-98ca-9b68b13974a9">

## PART 3

I didn't know that I could change the behavior of my code based on the URL. Previously, I had thought that only user input could change a program, and had never really looked at the 
URL as a tool that I could utilize. 







