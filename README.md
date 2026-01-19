# setup infra
**AWS CLI Installation:**

````
sudo apt install unzip -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
````
````
aws --version
````
**Terraform Installation:Ubuntu**
````
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
````
````
terraform --version
````
**Set Up aws profile**
````
aws configure --profile "tf-user"
````
-  provide acccess key
-  provide secret key
-  region

**add profile to provider.tf**
```tf
provider "aws {
 region = "ap-southeast-1"
 profile = "tf-user"
}
```

#### Changes:
- **main.tf** instance-type
- **main.tf** bucket-name

**Initialize terraform**
````
terraform init
````
