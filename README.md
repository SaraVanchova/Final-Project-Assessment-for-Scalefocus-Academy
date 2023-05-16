 # Final-Project-Assessment-for-Scalefocus-Academy

### Using Minikube, Helm, Jenkins


**1. Cloning the github repo for bitnami** 
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/8c9fa44b-ae08-42e3-95ee-b5faa518a2c0)</br>
*Problems encountered: /*

**2. Building helm dependencies**
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/14391ac3-0684-4181-8166-c7434006fafd)</br>
*Problems encountered: /*

**3. Changing the values.yml file on line 534 from LoadBalancer to ClusterIP** 
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/200df864-a4e7-4307-a11d-103615f1b77a)
 
   **3.1 Install helm**
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/006300be-00fd-49f0-9105-c77ad50b91cb)
   **3.2 Check if pods are up and running**
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/8c5e268f-63c5-4334-83a7-eaf8d8745103)
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/09ab942f-0705-45d8-9f16-c1373a175b2b)</br>
 *Problems encountered: /*    
 
**4. Create Jenkins pipeline with content uploaded on ->** [pipeline](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/blob/main/pipeline)</br>
*Everything is explined with comments in the pipeline file* </br></br>
*Problems encountered: <br>1. Had to configure Kubernetes on Jenkins: Installment of Kubernetes plugins, In manage nodes and cloudes -> set up kubernetes cloud, in 
Manage Jenkins -> Credentials had to upload the .kube config file.
  </br>2.Creating pipeline encountered issuess:</br>
       2.1 ![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/7e719afc-52a8-4fe1-9465-4eb48675e669) I resolved this with changing the \ -> / in the file path and deleteing C:.
  </br>2.2 ![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/b532f37b-9c2e-4185-8733-14e355fd72d3)
Failed to create namespace but it already exist, i fixed this by changing the condition in the pipeline syntax.*

**5. Deploy on Jenkins**
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/4f29b3db-4af2-4329-8da7-0fe90f2dc02e)
</br>The connections is ongoing I can access the page at anytime if the docker minikube is running and when i quit the docker.

**6. Go to ip 127.0.0.1:80**
![image](https://github.com/SaraVanchova/Final-Project-Assessment-for-Scalefocus-Academy/assets/125595064/2ab46e70-65a0-44fb-840c-1a62250d48af)<br><br>




