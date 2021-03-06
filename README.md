# Nucleus SDK
Nucleus SDK with instructions and examples on how to use Nucleus APIs

## Prerequisites
1. Python 3.5 or newer is set up in a virtual environment. More details: https://docs.python.org/3/tutorial/venv.html
2. Java 7 or 8 is installed. More details: https://www.oracle.com/technetwork/java/index.html 

## Python SDK Generation
The starting point of all command sequence is the root of the repository.  
1. Install Swagger Generator  
   Below are quick-start instructions for the operations systems that we have tested. For more details or OS not listed below please refer to https://github.com/swagger-api/swagger-codegen .
  * MacOS:   
    `brew install swagger-codegen`
  
  * Ubuntu:   
    ```
    cd swagger
    wget http://central.maven.org/maven2/io/swagger/swagger-codegen-cli/2.3.1/swagger-codegen-cli-2.3.1.jar -O swagger-codegen-cli.jar
    cd ..
    ```

2. Run Swagger Code Generator to generate Nucleus client Python module
  * MacOS:  
    ```
    cd swagger
    swagger-codegen generate -i nucleus-api-swagger.json -l python -c config.json -o sdk
    cd ..
    ```

  * Ubuntu:  
    ```
    cd swagger
    java -jar swagger-codegen-cli.jar generate -i nucleus-api-swagger.json -l python -c config.json -o sdk
    cd ..
    ```

3. Install Nucleus client Python module. This step assumes that you are running python from a Python3 virtual environment
```
cd swagger/sdk
python3 setup.py install
cd ../..
```

## Python SDK Documentation
The documentation on all available APIs can be found in swagger/sdk/README.md and swagger/sdk/docs

## Example using Nucleus APIs
1. Go to the examples directory `cd examples`
2. Open analyze-trump-tweets.py in a text editor and update the lines below with provided host name and API key  
    ```
    configuration.host = 'API_HOST_HERE'
    configuration.api_key['x-api-key'] = 'API_KEY_HERE'
    ```
3. Execute the example: 'python3 analyze-trump-tweets.py' 
