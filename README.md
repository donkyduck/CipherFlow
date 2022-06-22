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
CipherFlow is a visual data flow tool for creating a [Node-RED](https://github.com/node-red/node-red) flow to represent a computation function on ciphertext in the Fully Homomorphic Encryption format.  
<!-- Getting Started -->
## Getting Started
The CipherFlow is a Node-RED toolkit that builds FHE cipher nodes on Node-RED platform.
* Prerequisites
  * Docker
  * Node-RED

* Installation 

```
nmp install
docker run -u 0 -p 1900:1880 --name cipherflow3  nataset/node-red-seal:0.1.1
```
 

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
  * Modified FHE Evaluator
    * Maximum : find the maximum value between two ciphertexts, ![equation](https://latex.codecogs.com/svg.image?%5Cmax(c_1,c_2)%20=%20%5Cfrac%7Bc_1&plus;c_2%7D%7B2%7D%20&plus;%20%5Cfrac%7B%5Csqrt%7B(c_1-c_2)%5E2%7D%7D%7B2%7D)
    * Minimum : find the minimum value between two ciphertexts, ![equation](https://latex.codecogs.com/svg.image?%5Cmin(c_1,c_2)%20=%20%5Cfrac%7Bc_1&plus;c_2%7D%7B2%7D%20-%20%5Cfrac%7B%5Csqrt%7B(c_1-c_2)%5E2%7D%7D%7B2%7D)
    * Square root : 
    * Divider : 
* FHE schemes :
  * [CKKS](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://eprint.iacr.org/2016/421.pdf)
    * Allow us to compute over real number with an approximation
    * Compress a vector of values into a message by an encoding technique. 
  * [BGV]()
  * [BFV]()