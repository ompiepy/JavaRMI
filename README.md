# JavaRMI
Implementation of JAVA RMI

### Step-by-Step Instructions:

1. **Compile the Java Files:**
    Save the three classes (`RmiServerIntf.java`, `RmiServer.java`, `RmiClient.java`) in the same directory.

    ```sh
    javac RmiServerIntf.java RmiServer.java RmiClient.java
    ```

2. **Generate Stub (if necessary):**
   > **Note:** Note that since version 5.0 of J2SE support for dynamically generated stub files has been added, and `rmic` is only provided for backwards compatibility with earlier     runtimes, or for programs that don't provide an explicit port number (or zero) when exporting remote objects, which is required for generated stubs to be possible, as described in the   `Javadoc` for `UnicastRemoteObject`.

   If using a JDK version prior to 5.0 or if required for compatibility:

    ```sh
      rmic RmiServer
    ```

3. **Start the RMI Registry:**
    Open a command prompt or terminal and start the RMI registry in the directory where your classes are located.

    ```sh
    rmiregistry
    ```

    Leave this terminal open as the RMI registry needs to run continuously.

4. **Run the RMI Server:**
    Open a new command prompt or terminal in the same directory and run the RMI server.

    ```sh
    java RmiServer
    ```

    You should see output indicating that the RMI server has started and the RMI registry is created or already exists, followed by the server being bound in the registry.

5. **Run the RMI Client:**
    Open another new command prompt or terminal in the same directory and run the RMI client.

    ```sh
    java RmiClient
    ```

    You should see the message "Hello World" printed in the terminal, which indicates that the client successfully invoked the remote method on the server.

