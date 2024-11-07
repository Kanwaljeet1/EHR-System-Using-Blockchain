<img src="https://www.devteam.space/wp-content/uploads/2018/02/health-730x410.png" align="right" hspace="1" vspace="1" height="120" width="200">

# EHR System

Electronic Health Record system of patient records, so that you never have to carry your medical files to a doctor again!

---

## Developers and Maintainers
The project is developed and maintained by
- Akshat Jain ([Akshat-Jain](https://github.com/Akshat-Jain))
- Shubhankar Amitabh ([shubhamitabh](https://github.com/shubhamitabh))
- Ravi Kishan ([ravi-kishan](https://github.com/ravi-kishan))
- Ashwani Yadav ([ashwaniYDV](https://github.com/ashwaniYDV))
<table>
<tr>
<td>


## Problem Statement
Over decades, medical facilities have evolved elegantly. Still most of us are the witness of the fact that whenever we see a doctor, we need to put forward our medical file in front of him/her. Our file contains our previous prescriptions, medical reports, X-Rays, MRIs etc. It is a tedious task to keep record of all these.

## Aim of the Project
We aim to provide a digital solution to this problem so that next time when you visit your doctor, you don’t need to carry your medical file. We will be using Blockchain technology to store the patient records. This will ensure that the information remains secure while being decentralised across different peers.

The basic idea is to use Blockchain for storing patient records. The workflow would be as follows:
1. Anyone can register on the Blockchain network as a doctor or a patient.
2. Whenever a patient visits a doctor, the doctor will have the required permissions to store the diagnosis and medical logs in the patient’s record which would be stored in distributed ledgers across the Blockchain network.
3. The doctor would require to sign in the transaction (which would be cryptographically encrypted with his private key) to create and modify the records of a patient (who would be uniquely identified by a patient ID).
4. The medical records of a patient will be accessible from any hospital.


## Why Blockchain?

### Security
Blockchain provides a secure way of managing records.
### Public Health
By using blockchain technology, regulatory bodies can create a shared stream of de-identified patient information.
### Managed Consent
Patients can specifically authorise any individual to access their medical information.
### Simplified Claim Processing
Blockchain technology can simplify the complex medical billing process by eliminating the series of validations and multiple third parties acting on behalf of other entities.
### Patient Generated Data
Patients will be able to easily upload and securely store their updated medical information without messing up any previous records.

## Tech Stack used for the project
* IBM’s Hyperledger Framework for Blockchain
* Hyperledger Composer based on Fabric Architecture
* Hyperledger Playground for Blockchain
* JavaScript for website
* Java for creating Android app

# Instructions to run the API Backend
- Clone the repo `git clone https://github.com/Akshat-Jain/EHR-System.git`
- CD into the cloned directory using `cd EHR-System`.
- First install [Hyperledger composer](https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html). Then install the [development environment](https://hyperledger.github.io/composer/latest/installing/development-tools.html).
- Execute the following commands to setup your Blockchain network and generate Hyperledger Composer Rest Server:
- `composer archive create -t dir -n .`
- `composer network install --card PeerAdmin@hlfv1 --archiveFile ehr@0.0.3.bna`
- `composer network start --networkName ehr --networkVersion 0.0.3 --card PeerAdmin@hlfv1 --networkAdmin admin --networkAdminEnrollSecret adminpw --file networkadmin.card`
- `composer card import --file networkadmin.card` 
- `composer-rest-server -c admin@ehr -n always -u true -d y -w true`
- Goto `http://localhost:3000/explorer` to explore the REST API

# Instructions to restart the server
- Change to the directory where the docker-compose.yml file is (`cd /Users/AkJn/fabric-dev-servers/fabric-scripts/hlfv1/composer`
- Run `docker-compose stop` to stop the Fabric Containers.
- Run `docker-compose start` to restart where you left off.
- Change to the cloned repo's directory: `cd /Users/AkJn/Projects/Blockchain/EHR-System`
- Run this command to start the server: `composer-rest-server -c admin@ehr -n always -u true -d y -w true`
- Goto `http://localhost:3000/explorer` to explore the REST API.

# Client Repositories for the Project

### Repo Link for Web Client:
https://github.com/ashwaniYDV/WebClient

### Repo Link for Android Client:
https://github.com/ravi-kishan/AndroidClient

## License

This project is available under the MIT license. See the [LICENSE](LICENSE) file for more info.
