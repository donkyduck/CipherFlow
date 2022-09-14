# CipherFlow
Node-red flow creator for Fully Homomorphic Encryption (FHE) 
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#References">References</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
CipherFlow is  a tool to create a visual data flow based on the Node-RED platform that allows the user to play with the data encryption and decryption based on the Fully Homomorphic Encryption (FHE) with the CKKS scheme.  The CipherFlow is aimed to simplify the way the IoT developers to develop their privacy preserving IoT solutions without hard-code program. The IoT developers just drag and drop the FHE nodes on the Node-RED workspace and wire the relevant nodes to complete the flow. 
<!-- Getting Started -->
## Getting Started
The CipherFlow is a Node-RED toolkit that builds FHE cipher nodes on Node-RED platform.
* Prerequisites
  * [Node-RED](https://nodered.org/docs/getting-started/)
  * [Docker](https://www.docker.com/)


* Installation </br>
There are 2 options:
  * [Install on the terminal](https://www.npmjs.com/package/node-red-cipherflow)
  ```
  cd ~/.node-red
  npm install node-red-cipherflow
  ```

  * Install in docker
  ```
   docker run -it -u root --name cipherflow-0.1.10-white -p 2005:1880 nataset/node-red-cipherflow:0.1.10_arm64
  ```

<!-- USAGE -->
## Usage

### CipherFlow Node Extension

The CipherFlow provides 2 types of node extension: 1) HE operation (yellow nodes) and 2) Arithmetic operation (blue nodes). <br/>
![](https://github.com/donkyduck/CipherFlow/blob/main/Figure/NodeExtension.png)

### CipherFlow Workspaces

CipherFlow has 3 types of workspace that allow each user create his/her data flows with respect to the functionalities: 
1. Playground: The Node-RED workspace that allows the IoT developers to construct their Node-RED CipherFlow and verify the correctness of the results from the computation over the encryption. Therefore, in this workspace, CipherFlow offers an "input" node to perform an initial input data and to encrypt this data with the chosen CKKS configuration.
    * Chain-Index is an indicator to hint at an IoT developer the maximum number of multiplications the flow can perform.
    
![](https://github.com/donkyduck/CipherFlow/blob/main/Figure/Example_playground.png)

![](https://github.com/donkyduck/CipherFlow/blob/main/Figure/Example_Reciprocal.png)

2. Edge: The Node-RED workspace that allows the IoT developers to construct the encryption flow.

![](https://github.com/donkyduck/CipherFlow/blob/main/Figure/Edge_flow.png)


3. Cloud: The Node-RED workspace that allows the IoT developer to construct the computation flow based on the HE operations. 
  * Instead of using an input node, in the cloud, the setContext is used to set the HE environment same as that of the edge. 
![](https://github.com/donkyduck/CipherFlow/blob/main/Figure/Cloud_example.png)

<!-- Reference -->
## Reference
* FHE library based on [node-SEAL](https://docs.morfix.io/) 
  * [FHE Evaluator](https://docs.morfix.io/Evaluator.html) supports the following operations:
    * Multiply : two ciphertexts,  ![equation](https://latex.codecogs.com/svg.image?c_1%20%5Ctimes%20c_2)
    * Add : additive two ciphertexts, ![equation](https://latex.codecogs.com/svg.image?c_1%20&plus;%20c_2)
    * Sub : divide two ciphertexts, ![equation](https://latex.codecogs.com/svg.image?c_1%20-%20c_2%20) 
    * Square : square root of ciphertext, ![equation](https://latex.codecogs.com/svg.image?%5Csqrt%7Bc%7D%20%20)
    * MultiplyPlain : Multiply a ciphertext with a plaintext, ![equation](https://latex.codecogs.com/svg.image?a*c_1%20%20)
    * AddPlain : Add a plaintext to a ciphertext, ![equation](https://latex.codecogs.com/svg.image?a%20&plus;%20c_1%20%20)
    * SubPlain : Sub a plaintext to sub, ![equation](https://latex.codecogs.com/svg.image?c_1%20-%20a%20)
    * SumElements : Sum all elements in the ciphertexts, ![equation](https://latex.codecogs.com/svg.image?%5Csum%7B%5Ctextbf%7Bc%7D%7D%20=%20%5Csum_%7Bi=1%7D%5E%7BN%7D%7Bc_i%7D), where ![equation](https://latex.codecogs.com/svg.image?c_i%20%5Cin%20%5Ctextbf%7Bc%7D)
  * CipherFlow extension for FHE Evaluator
    * Reciprocal : find the multiplicative inverse (1/x) of ciphertext based on the modified Goldshmidt iterative methods.
* FHE schemes :
  * [CKKS](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://eprint.iacr.org/2016/421.pdf)
    * Allow us to compute over real numbers with approximation
    * Compress a vector of values into a message by an encoding technique. 
  