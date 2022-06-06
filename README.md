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
The CipherFlow is a library based on [Node-RED](https://github.com/node-red/node-red) that allows low-code programming on FHE.  

<!-- Reference -->
## Reference
* FHE library based on [node-SEAL](https://docs.morfix.io/) 
  * [FHE Evaluator](https://docs.morfix.io/Evaluator.html) supports the following operations:
    * Multiply : two ciphertexts,  ![equation](https://latex.codecogs.com/svg.image?c_1%20%5Ctimes%20c_2)
    * Add : additive two ciphertexts, ![equation](https://latex.codecogs.com/svg.image?c_1%20&plus;%20c_2)
    * Sub : divide 2 ciphertexts, ![equation](https://latex.codecogs.com/svg.image?c_1%20-%20c_2%20) 
    * Square : square root of ciphertext, ![equation](https://latex.codecogs.com/svg.image?%5Csqrt%7Bc%7D%20%20)