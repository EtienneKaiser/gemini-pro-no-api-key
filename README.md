## 🎙️ Introduction

As everybody should have heard of at least by now, is that Google released a new flagship model called [Gemini](https://blog.google/technology/ai/google-gemini-ai/). I won't go into its capabilities but rather into how to access it. Currently there is an API-Key role-out for [specific regions](https://ai.google.dev/available_regions) only. Those locations can [obtain an API-Key using the makersuite](https://makersuite.google.com/) **but all other countries below cannot!**

## 🛒 What ingredients do we need?

- A Google Cloud Console Account - some regions offer $300 bucks trial balance, we don't need it!
- A credit card - for validation purpose if you need to create a new GCP account only!
- Some patients - nobody likes to read manuals but I tried to keep it concise ;)

After following the setup steps you are able to generate your first requests which will be exported in a file called `output.csv` by default.

**Let's begin!**

## ☁️ Setup on Google Cloud Platform (GCP)

#### Step 1: Create a Google Cloud Account

1. Go to the [Google Cloud Console](https://cloud.google.com/?hl=en).
2. Click on `Get Started for Free` if you don't have a Google Cloud account. Follow the prompts to create an account.

#### Step 2: Create a New Project

1. Once logged in, click on the project dropdown in the upper-left corner of the Cloud Console.
2. Click on the `New Project` button.
3. Enter a `Gemini Pro Project`, select an Organization if applicable, and choose a Location (region).
4. Click on the `Create` button.

#### Step 3: Enable Billing for the Project

1. In the Cloud Console, navigate to the `Billing` section.
2. Click on `Link a billing account` and follow the instructions to set up billing for your project.

#### Step 4: Enable APIs

1. In the Cloud Console, go to the `APIs & Services` -> `Dashboard` section.
2. Click on the `+ ENABLE APIS AND SERVICES` button.
3. Search for the APIs you need (e.g., `Cloud Storage API`, `AI Platform API`) and enable them.

#### Step 5: Create Service Account and Download Key File
1. In the Cloud Console, go to the `IAM & Admin` -> `Service accounts` section.
2. Click on `+ CREATE SERVICE ACCOUNT`.
3. Enter a Service account name, select a role (e.g., `Gemini Pro Project` -> `Owner` for full access), and click `Continue`.
4. Optionally, you can add additional permissions and click `Continue`.
5. Skip the `Grant users access to this service account` section and click `Done`.
6. Find the newly created service account in the list and click on the pencil icon (edit).
7. Navigate to the `Add Key` tab, select `JSON`, and click `Create`. This will download a JSON key file (`keyxxx.json`) which we need in the following part!

## 🌐 Setup Environment

#### Step 6: Set Environment Variable
1. Place the downloaded`keyxxx.json` file in the same directory as the notebook.

**Note:** In a productive environment we would use a Key-Vault to store credentials. Further in the code you will see a part where a the file is retrieved with the credentials. Even it's less secure, we don't use more strict requirements as it serves the sake of simplicity.

**Good news - You are done with paperwork!**
