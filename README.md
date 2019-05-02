# Module 5a - Beginner Lab: Key Strength

## Background
In applications of cryptography, all of the weight of security depends on the maintanence of some secret (a secret key); however, secrecy is in-turn sometimes dependent upon entropy, and this dependence may lead to compromised accounts, lost funds, and similar terrible happenings when the entropy is not sourced or managed responsibly. A relevant example is the discovery of the so-called Blockchain Bandit. In [the associated article][blockchain-bandit], at least one entity has been stealing millions of dollars worth of ETH by taking advantage of other users' private keys which are technically valid yet laughably insecure due to their effective length. (Every key is 256 bits long, but some wallet software or user choices resulted in effectively shorter keys by filling remaining space with zeroes.) In this lab, we will generate keys using coin flips and observe how the length of the keys affects their security. In the context of this lab, the compromised users and/or their wallet software did what is akin to our first set of only 5 coin flips.

## Meta Information
| Attribute | Explanation |
| - | - |
| Summary | Students will flip a coin a total of 15 times each. The presence of bit-string (key) collisions will be checked after 5 and 15 flips. |
| Topics | Cryptography, secret keys, collisions, and randomness. |
| Audience | CS1 or later. |
| Difficulty | Beginner. |
| Strengths | Demonstrates weak keys, strong keys, and a method of key generation. |
| Weaknesses | Requires use of survey form and online spreadsheet or significant writing space and time to analyze results. For a class size of 20, the probability of at least one collision after 5 flips and no collisions after 10 more (a good example of weak and strong keys) is only about 99.38%. |
| Dependencies | Enough coins for flipping, and internet-connected computers with suitable browsers or a whiteboard or similar. |
| Variants | This lab is designed for a class size of approximately 20, but the number of coin flips at each stage should be adjusted for significantly different class sizes. |

## Assignment Instructions (student)
1. Open the [online response form][key-submission-form].
2. Enter your name.
3. Flip a coin 5 times and record the result in the appropriate field.
4. Flip the coin 10 more times and record the result in the appropriate field.
5. Submit your response.
5. Wait for the proctor to collect all responses and sort them to allow for detection of collisions.
6. Observe how there was (probably; 99.96% chance) at least one collision after only 5 coin flips.
7. Observe how there were (probably; 99.42% chance) no collisions after 15 coin flips.
8. Finally, note that 15-bit keys are NOT actually secure, since a modern laptop can easily check all 2^15 possible keys in little time (e.g. 0.0007 seconds). In contrast, there is not enough computing power in the world to crack a 256-bit ECDSA signature as used in cryptocurrencies (although it is not quite as simple as just iterating through the 2^256 possibilities).

## Assignment Instructions (proctor)
1. Share this lab and potentially the [online response form][key-submission-form], otherwise be prepared to collect and analyze results by hand via whiteboard or similar.
2. Once all results are collected, use the spreadsheet button on the editing view of the form to open the results in a spreadsheet on a screen the entire class can see.
3. The results will first be in timestamp order. Right click the column containing data for the first 5 flips, and select the option to sort them from A -> Z.
4. Highlight rows where the first 5 flips are identical (they should now be grouped together) and explain how these 5-bit strings represent the same key and are known as collisions, how the presence of collisions compromises the security of the key holder, and how the short length of the keys allows an adversary with sufficient computing power to crack them by iterating through all possible keys.
5. Right click the column containing data for the next 10 flips, and select the option to sort them from A -> Z. Now do the same for the column containing the first 5 flips again.
    * This works to align potential collisions while demonstrating that there are (probably) no collisions, since the sorting algorithm is stable.
6. Attempt to locate any rows where all 15 flips match (they should now be grouped together, if they exist) and explain how the (probable) lack of any collisions makes these keys secure.
7. It is important to note that these keys are not actually secure, since it would take a computer very little time to iterate through and check all of the 2^15 possible keys, but this is a good example of how key length affects key strength.

## Credits
Dr. Debasis Bhattacharya  
Mario Canul  
Saxon Knight  

[blockchain-bandit]: https://www.wired.com/story/blockchain-bandit-ethereum-weak-private-keys/
[key-submission-form]: https://forms.gle/SeyW2piWgBm1gP2z9
