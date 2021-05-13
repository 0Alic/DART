# :dart: DART: DecentrAlized Role-based Trust management

DART is an Ethereum implementation of the Role-based Trust management (RT) framework. In particular, the implementation is restricted to the sub-language RT0 of the RT family.

Being Alice, Bob *principals*, x, y *role names*, Alice.x, Bob.y *roles*, the RT0 credentials are:
- Simple member: Alice.x &larr; Bob
- Simple inclusion: Alice.x &larr; Bob.y
- Linked inclusion: Alice.x &larr; Bob.y.z
- Intersection inclusion: Alice.x &larr; Bob.x &cap; Charlie.z

DART allows a user to create policies composed by RT0 credentials, plus adding a weight *w* &in; (0, 100] that reflects the trust a user puts into a particular role. In this way, policies can either used for both hard-security purposes (yes/no answer), and soft-security purposes (answer with a degree of acceptance).

In DART, policies are stored on a public blockchain, meaning they are secured by the blockchain consensus, they are transparent, and they cannot be arbitrally altered by any third party.

Finally, DART supports the execution of the backward search discovery algorithm, which processes the credentials and answers to the following query: "Given a role A.r, find its set of members along with their trust values".

The implementation is in Ethereum for prototyping and evaluation purposes, but the approach can be translated into other blockchain networks.

## Structure of the repository

This is a Truffle project. The DART smart contract is in *contracts/RT.sol*. The *test/* folder contains the scripts to test the correctness of the smart contract. The *exec/* folder contains the scripts to evaluate the cost in gas of DART.

## Contributors

The project has been developed by [lucaceschi](https://github.com/lucaceschi), with the support of [andreadesalve](https://github.com/andreadesalve) and [0Alic](https://github.com/0Alic).

This work is part of a research on blockchain technology and trust management systems. The rest of the contributors can be found on the upcoming paper related to this project.

## References

RT framework papers: [Design of a role-based trust-management framework](https://ieeexplore.ieee.org/abstract/document/1004366?casa_token=R_H0efcz51oAAAAA:ZVyPlVbJcMcT8HSW8_A_Nat6KYFWxRCVoqPGB7jsd-4ES3_-ElFARLLYJHvkOpwsax8kQ4_wrg) Ninghui Li et al.; [RT: a Role-based Trust-management framework](https://ieeexplore.ieee.org/abstract/document/1194885?casa_token=Hur5B31um3YAAAAA:P4LyjDr2SuqbOw7wXlnnHWpU8dyWeKr97PeV7OiQaHAxsGZP9Eelihh1h2AB65EGWziSValFhQ) Ninghui Li et al.

Chain discovery algorithms: [Distributed credential chain discovery in trust management](https://content.iospress.com/articles/journal-of-computer-security/jcs169) Ninghui Li et al.

