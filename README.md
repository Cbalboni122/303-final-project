# 303-final-project
Here is the link to the Azure Foundry project: https://portal.azure.com/#@carsonbalbonigmail.onmicrosoft.com/asset/Microsoft_Azure_ProjectOxford/AIFoundryProject/subscriptions/f59daf2a-7afa-490f-8170-d8ae29b782dc/resourceGroups/rg-carson.balboni-5890/providers/Microsoft.CognitiveServices/accounts/carsonbalboni5890-resource/projects/carsonbalboni5890

The code is provided in the file named agent_code.

PROJECT SETUP:

To set up and run this project, first a Microsoft Azure account is needed, as we will use the connectivity of this program to create our agent.
These instructions assume that this account is created and is using the "Microsoft Student Account", which gives access to $200 worth of free AI power.
This $200 allows us to access certain tools like their internet data scrubber.

Step 1: Create an AI Foundry Project inside your account.

Step 2: Navigate to the agents tab inside the Foundry project and create a base agent.
  Step 2.1: For this project, we use a connection to GPT 4, as this allows us to access
    all of the development tools inside of Azure. This is chosen upon the creation of the
    base agent. 
    
Step 3: Now that we have created the agent, we have access to all of the tools. The first
  tool we will use is the model description. This gives a baseline for the model to base its
  responses on. We use this script: "This agent's goal is to take the provided emails from the user 
  and check them for suspected phishing scams. The check should look at the sender, the subject line, 
  and the contents of the email itself. If the information is suspicious and suspected of being a
  phishing scam, return the likelihood on a scale of 100, 1 being lowest, and why."
  
  Step 3.1: This prompt gives the model an idea of what to output to the user. It helps
    to minimize what information the user sees. 
    
Step 4: Now the agent needs access to the internet and the database that we are using. We then
  move down to the "Knowledge section" of Azure. Here, we can add a connection to the internet and
  to our database. However, the AI does not know what information to look for inside our database.
  For this, we need to fine-tune the model
  
Step 5: We now save the model and move to the "Fine-tuning" section of Azure. Here, we run our model
  and start to filter out the responses that we don't want the model to respond to. This is where we
  create how we want the model to reply specifically.
  
Step 6: Now that the model knows how to organize its response, it needs to know how to use the information
  provided to it. Inside the CSV file we gave, there are tens of thousands of scam emails. The model goes through
  the database and takes in the email addresses and the body of the email, and learns how they are structured. 
  This is how the AI model learns what to detect.
  
Step 7: With the Model now trained on the database, we use the internet connection we established above to continue
  to train the model on scam emails.
  
Step 8: For this step, the model must now be trained on good, clean emails so it can tell the difference. For my
  project, I ran out of the free resources before I was able to complete this training. Because of this, my model
  would return false positives on a higher-than-wanted average, with the safe rating for my project being values less
  than 50%. 
  
Step 9: Clone the model. In the clone model, move to the "Connected Agents" tab and add the base model to the clone one.
  Doing this opens up the resources again for the new model.
  
  Step 9.1: inside the "Connected Agents" tab, set the base model trigger to the user interacting with the clone model.
  This way, the base model can affect the output of the clone. 

Future improvements:
  To improve this project in the future, I would need to train it using safe emails to lower the rate of false positives.
  Having the safe value being anything under 50 is inefficient and could lead to problems in the future.

  Not only that, but putting in more money instead of the free model would allow me to train the base model better instead
  of having to clone it every time I run out of the free resources.
  
  Also, having the model be able to connect directly to an email instead of being an outside tool that requires the user
  to copy and paste a suspected scam email would make this project much more efficient.
  
