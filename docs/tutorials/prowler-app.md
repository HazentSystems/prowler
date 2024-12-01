# Prowler App

The **Prowler App** is a user-friendly interface for the Prowler CLI, providing a visual dashboard to monitor your cloud security posture. This tutorial will guide you through setting up and using the Prowler App.

After installing the **Prowler App**, access it at [http://localhost:3000](http://localhost:3000).
You can also access to the auto-generated **Prowler API** documentation at [http://localhost:8080/api/v1/docs](http://localhost:8080/api/v1/docs) to see all the available endpoints, parameters and responses.

## **Step 1: Sign Up**
To get started, sign up using your email and password:

<img src="../../img/sign-up-button.png" alt="Sign Up Button" width="320"/>
<img src="../../img/sign-up.png" alt="Sign Up" width="285"/>

---

## **Step 2: Log In**
Once you’ve signed up, log in with your email and password to start using the Prowler App.

<img src="../../img/log-in.png" alt="Log In" width="350"/>

---

## **Step 3: Add a Provider**
To run your first scan:

1. Navigate to `Settings > Providers`.
2. Click `Add Account` to set up a new provider and provide your credentials:

<img src="../../img/add-provider.png" alt="Add Provider" width="700"/>

---

## **Step 4: Configure the Provider**
Choose the provider you want to scan from the following options:

- **AWS**: Enter your AWS Account ID.
- **GCP**: Enter your GCP Project ID.
- **Azure**: Enter your Azure Subscription ID.
- **Kubernetes**: Enter your Kubernetes Cluster name.

Optionally, provide a **Provider Alias** for easier identification. Follow the instructions provided to add your credentials:

<img src="../../img/add-account.png" alt="Add Account" width="700"/>

---
### **Step 4.1: AWS Credentials**
For AWS, Prowler App can use either IAM Access Keys or assume an IAM Role. Here’s how to set up each:

#### **Step 4.1.1: IAM Access Keys**
1. Select `Connect via Credentials`.

    <img src="../../img/connect-aws-credentials.png" alt="AWS Credentials" width="350"/>

2. Enter your `Access Key ID`, `Secret Access Key` and optionally a `Session Token`:

    <img src="../../img/aws-credentials.png" alt="AWS Credentials" width="350"/>

#### **Step 4.1.2: IAM Role**
1. Select `Connect assuming IAM Role`.

    <img src="../../img/connect-aws-role.png" alt="AWS Role" width="350"/>

2. Enter the `Role ARN` and any optional field like the AWS Access Keys to assume the role, the `External ID`, the `Role Session Name` or the `Session Duration`:

    <img src="../../img/aws-role.png" alt="AWS Role" width="700"/>

---

### **Step 4.2: Azure Credentials**
For Azure, Prowler App uses a Service Principal to authenticate. See the steps in https://docs.prowler.com/projects/prowler-open-source/en/latest/tutorials/azure/create-prowler-service-principal/ to create a Service Principal. Then, enter the `Tenant ID`, `Client ID` and `Client Secret` of the Service Principal.

<img src="../../img/azure-credentials.png" alt="Azure Credentials" width="700"/>

---
### **Step 4.3: GCP Credentials**
To connect your GCP Project, you need to use the Application Default Credentials (ADC) returned by the `gcloud` CLI. Here’s how to set up:

1. Run the following command in your terminal to authenticate with GCP:
```bash
gcloud auth application-default login
```
2. Once authenticated, get the `Client ID`, `Client Secret` and `Refresh Token` from `~/.config/gcloud/application_default_credentials`.
3. Paste the `Client ID`, `Client Secret` and `Refresh Token` into the Prowler App.

<img src="../../img/gcp-credentials.png" alt="GCP Credentials" width="700"/>

---
### **Step 4.4: Kubernetes Credentials**
For Kubernetes, Prowler App uses a `kubeconfig` file to authenticate, paste the contents of your `kubeconfig` file into the `Kubeconfig content` field.

By default, the `kubeconfig` file is located at `~/.kube/config`.

<img src="../../img/kubernetes-credentials.png" alt="Kubernetes Credentials" width="700"/>

---

## **Step 5: Test Connection**
After adding your credentials of your cloud account, click the `Test Connection` button to verify that the Prowler App can successfully connect to your provider:

<img src="../../img/test-connection-button.png" alt="Test Connection" width="700"/>


## **Step 6: Start Your First Scan**
After successfully adding and testing your credentials, click the `Start Now` button to initiate your first scan:

<img src="../../img/start-now.png" alt="Start Now" width="700"/>

???+ note
    Prowler will automatically scan all configured providers every **24 hours**, ensuring your cloud environment stays continuously monitored.
---

## **Step 7: Monitor Scan Progress**
Track the progress of your scan in the `Scans` section:

<img src="../../img/scan-progress.png" alt="Scan Progress" width="700"/>

---

## **Step 8: Analyze the Findings**
While the scan is running, start exploring the findings in these sections:

- **Overview**: High-level summary of the scan.
- **Findings**: Detailed list of issues detected. <img src="../../img/findings.png" alt="Findings" width="700"/>
- **Compliance**: Insights into compliance status. <img src="../../img/compliance.png" alt="Compliance" width="700"/>
- **Services**: Breakdown of services scanned. <img src="../../img/services.png" alt="Services" width="700"/>