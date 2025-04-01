## Lab 1: Environment Setup

<walkthrough-tutorial-duration duration="20"></walkthrough-tutorial-duration>
<walkthrough-tutorial-difficulty difficulty="2"></walkthrough-tutorial-difficulty>

Let's build the first step in the Data Journey.
In this lab we will set up your environment and set up a messaging stream for our data.

We have to make sure your GCP project is prepared:

Clone the github repo we'll be using in this walkthrough:

```bash
git clone https://github.com/NucleusEngineering/data-journey
cd data-journey/Data-Simulator
```

We will be using Terraform to provision infrastructure and resources, setup Network, Service Account and Permissions. 
In addition, we will extracts a sample dataset from a public BigQuery table, build and deploy a sample app and create a Pub/Sub topic.

Want to know what exactly the Terraform configuration file does?

Let's ask Gemini:

1. Open Gemini Code Assist <img style="vertical-align:middle" src="https://www.gstatic.com/images/branding/productlogos/gemini/v4/web-24dp/logo_gemini_color_1x_web_24dp.png" width="8px" height="8px"> on the left hand side.
2. Insert ``What main.tf file do?`` into the Gemini prompt.


First, we need to change the terraform variable file. You can open files directly from this tutorial:
Open `./terraform.tfvars` <walkthrough-editor-open-file filePath="Data-Simulator/terraform.tfvars">by clicking here</walkthrough-editor-open-file> and add your own project id.

❗ Please do not include any whitespaces when setting these variablers.

Build the basic permissions & networking setup via terraform apply.

```bash
terraform init -upgrade
```

```bash
terraform apply -var-file terraform.tfvars
```

 ### Validate Event Ingestion

After a few minutes, we should have the proxy container up and running. We can check and copy the endpoint URL by running:

```bash
gcloud run services list
```

The endpoint URL refers to the URL of the proxy container deployed to Cloud Run with the streaming data input. 
We need to add GCP Project ID, the GCP Region and the endpoint URL in `./config_env.sh`<walkthrough-editor-open-file filePath="Data-Simulator/config_env.sh">by clicking here</walkthrough-editor-open-file>.


After, enter the variables in the config file. You can open it
<walkthrough-editor-open-file filePath="config_env.sh">
in the Cloud Shell Editor
</walkthrough-editor-open-file>
to read or edit it.

Set all necessary environment variables by running:

```bash
source config_env.sh
```

You can now stream website interaction data points through a Cloud Run Proxy Service into your Pub/Sub Topic.

The script `synth_json_stream.py` contains everything you need to simulate a stream. Run to direct an artificial click stream at your pipeline.

```bash
python3 synth_json_stream.py --endpoint=$ENDPOINT_URL --bucket=$BUCKET --file=$FILE
```

After a minute or two validate that your solution is working by inspecting the [metrics](https://cloud.google.com/pubsub/docs/monitor-topic) of your Pub/Sub topic. Of course the topic does not have any consumers yet. Thus, you should find that messages are queuing up.

By default you should see around .5 messages per second streaming into the topic.
