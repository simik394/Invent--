[[../Concepts/Retrieve Augmented Generation|RAG]]

# config howto
Certainly! To change the directory where **OLLAMA** stores its models, follow these steps:

1. **Create an Environment Variable**:
    
    - Open **Windows Settings**.
    - Go to **System**.
    - Select **About**.
    - Click on **Advanced System Settings**.
    - Navigate to the **Advanced** tab.
    - Click on **Environment Variables…**.
    - Create a new variable called **OLLAMA_MODELS**.
    - Set its value to the desired directory where you want to store the models.
2. **Specify the New Location**:
    
    - You can move the existing **Models** folder from the default location (usually `C:/Users/username/.ollama/models`) to the new directory you’ve chosen.
    - Alternatively, you can create a symbolic link between the original models folder and the new location using the `mklink` command. For example:
        
        ```
        mklink /D C:\Users\<User>\.ollama\models E:\AI\Ollama\Models
        ```
        
        The `/D` flag ensures that a directory symlink is created.
3. **Update the Environment Variable**:
    
    - After setting up the new location, restart **OLLAMA** or any relevant processes.
    - **OLLAMA** will now use the specified directory for storing its models.

Remember that this approach allows you to customize the storage location according to your needs. [Enjoy your updated model storage! 🚀](https://github.com/ollama/ollama/issues/2551)[1](https://github.com/ollama/ollama/issues/2551)[2](https://github.com/ollama/ollama/issues/1737)[3](https://github.com/ollama/ollama/issues/1165).