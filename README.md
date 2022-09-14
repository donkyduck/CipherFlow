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
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#References">References</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
CipherFlow is  a tool to create a visual data flow based on the Node-RED platform that allows the user to play with the data encryption and decryption based on the Fully Homomorphic Encryption (FHE).  
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
CipherFlow has 3 types of workspace that allow each user create his/her data flows with respect to the functionalities: 
1. Playground: The Node-RED workspace that allows the IoT developers to construct their Node-RED CipherFlow for their IoT solutions.
2. Edge: The Node-RED workspace that allows the IoT developers to construct the encryption flow.
3. Cloud: The Node-RED workspace that allows the IoT developer to construct the computation flow based on the HE operations. 


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
  