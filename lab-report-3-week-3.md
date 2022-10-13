# Charlotte Dong Lab Report3 (Week3)  
  
## Part 1 Simplest Search Engine (Week2)  
* Based on what we learned from lab2, we can create the simplest search engine. First, make a new file called **SearchEngine.java**, which should implement a web server. For example, I implemented **Server.java** in the wavelet repository.  
* This **SearchEngine.java** supports a path for adding new strings to the list as well as a path for searching and returning all strings containing a given substring.  
* Below is my code:  
  
  ```
class Handler implements URLHandler {

    ArrayList<String> lst = new ArrayList<>();
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Hello";
        }
        else if (url.getPath().contains("/add")) {
            String[] newstr = url.getQuery().split("=");
            for (String s : newstr){
                lst.add(s);
            }
            return "String added";
        }
        else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/search")) {
                String[] parameters = url.getQuery().split("=");
                String toReturn = "";
                if (parameters[0].equals("s")) {
                    for (String s : lst){
                        if (s.contains(parameters[1])){toReturn += " " + s;}
                        else {continue;}
                    }
                    return toReturn;
                }
            }
            return "404 Not Found!";
        }
    }
}
```  
```
class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```  

