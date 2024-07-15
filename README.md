## AI Moot Court Project


This project is forked from [Chatarena](https://github.com/Farama-Foundation/chatarena), with some modifications, to simulate a moot court environment using three AI agents.


## Getting Started

Note that Python >= 3.7 is required.  
To install and run the project:  

    pip install chatarena[all]  
    git clone https://github.com/HKUGenAI/AIMootCourt.git  
    cd AIMootCourt  
    ./start.sh  

Additionally note that the original OpenAI API call was changed to Azure OpenAI, in  

    AIMootCourt/chatarena/backends/openai.py  
    
You can convert it back to OpenAI API by following the original Chatarena code, if necessary.  

To use Azure OpenAI in your project, modify the following in `start.sh` :  

    export AZURE_OPENAI_API_KEY="your-api-key-here"  
    export AZURE_OPENAI_API_ENDPOINT="your-api-endpoint-here"  
    export AZURE_OPENAI_API_DEPLOYMENT_NAME="your-api-deployment-name-here"  


## Modifying the case

4 prompts are used to control the moot court simulation:  

1. A global prompt, which consists of the court rules for the AI to follow, as well as details and facts of the case.
2. A role description for the Plaintiff.
3. A role description for the Defendant.
4. A role description for the Judge.
   
To use our pre-built case, on the Web UI, select "NLP Classroom 3 Players" from the dropdown menu "Environments".  

To use your own test case and prompts, you can modify the text directly on the Web UI for a single trial, but the changes will not be saved.
To change the environment directly so the prompts are saved, you can modify the following file:  

    AIMootCourt/examples/nlp-classroom-3players.json
    
You may use the python file at `AIMootCourt/convert_to_string.py` to help convert a text prompt to the required json format.  

Finally, click "Run" on the Web UI to start the simulation.  



      
