# Agents for Amazon Bedrock Test UI

A generic Streamlit UI for testing generative AI agents built using Agents for Amazon Bedrock. For more information, refer to the blog post [Developing a Generic Streamlit UI to Test Amazon Bedrock Agents](https://blog.avangards.io/developing-a-generic-streamlit-ui-to-test-amazon-bedrock-agents).

# Prequisites

- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [Python 3](https://www.python.org/downloads/)

# Running Locally

1. Run the following `pip` command to install the dependencies:

   ```
   pip install -r requirements.txt
   ```

2. Set the following environment variables:
   - `BEDROCK_AGENT_ID` - The ID of the agent
   - `BEDROCK_AGENT_ALIAS_ID` - The ID of the agent alias. The default `TSTALIASID` will be used if it is not set.
   - The [AWS environment variables](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html) that provides the credentials to your account. The principal must have the necessary permissions to invoke the Bedrock agent.
3. (Optional) Set the folliowing environment variables to customize the UI:
   - `BEDROCK_AGENT_TEST_UI_TITLE` - The page title. The default `Agents for Amazon Bedrock Test UI` will used if it is not set.
   - `BEDROCK_AGENT_TEST_UI_ICON` - The favicon, such as `:bar_chart:`. The default Streamlit icon will be used if it is not set.
4. Run the following command to start the Streamlit app:

   ```
   streamlit run app.py --server.port=8080 --server.address=localhost
   ```
# Using in CloudShell
## 1. Install Streamlit
pip3 install streamlit --user

## 2. Download and Install ngrok
wget https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz

tar -xvzf ngrok-v3-stable-linux-amd64.tgz

chmod +x ngrok

sudo mv ngrok /usr/local/bin/

## 3. Create a Simple Streamlit App
echo "
import streamlit as st

st.title('Hello from AWS CloudShell!')
st.write('This is a simple Streamlit app running in CloudShell with ngrok.')
" > app.py

## 4. Run Streamlit App
streamlit run app.py --server.port=8080 --server.address=0.0.0.0 &

## 5. Run ngrok to Expose the Streamlit App
ngrok http 8080
