# Database Encryption using Facial Recognition
This project aims to encrypt/decrypt a database using facial encodings and string input.

## Requirements
1. OpenCV
2. numpy
3. secrets
4. string
5. pickle
6. pyminizip
7. hashlib

## Basic Understanding of the Project
- It takes your facial features and converts them into **Facial Encodings**.
- It then asks for user to enter a string input which is then used to create a **Unique Encryption Key**.
- The **Facial Encodings** and **Unique Encryption Key** (generated from the string input) are concatenated to create a **Final Encryption Key**.
- The **Final Encryption Key** is used to encrypt the database. 

## Why is it secure?
- This method only requires the user to store one form of data into the database (in this case facial encodings).
- Even if the database with facial encodings somehow gets hacked then the attacker would only have one part of the encryption key.
- Hence, until and unless the attacker has both part of the encryption key (facial encodings + unique encryption key), they won't be able to access the data.

## Existing Models
![image](https://github.com/atbashyal/Database-Encryption-using-Facial-Recognition/assets/68748665/ccf15c9c-4924-42d5-b9c7-4f3e1566d6bf)

## Proposed Model Architecture Diagram
![image](https://github.com/atbashyal/Database-Encryption-using-Facial-Recognition/assets/68748665/47142b57-3810-4ec3-ab59-6fbdf0f2ee9b)

## Flow Chart
![image](https://github.com/atbashyal/Database-Encryption-using-Facial-Recognition/assets/68748665/99ea3386-e53b-404a-b6b7-a89afe0a7929)

## Possibilities of Future Work
1. To explore different face recognition algorithms or techniques to improve the accuracy of facial recognition. This could involve experimenting with different feature extraction methods, such as using a deep learning approach with convolutional neural networks (CNNs), or exploring different face detection algorithms to improve the performance of the system. 
2. It would be beneficial to evaluate the proposed model on a larger scale to determine its scalability and practicality. Testing the system on a larger database with more users and data could provide insights into any potential performance or scalability issues, and help refine the system for real-world deployment.
3. The current system only uses facial recognition as one factor in generating the encryption key. Further research could be conducted to incorporate other biometric factors, such as fingerprint or iris recognition, to strengthen the security of the system.
4. Exploring the use of blockchain technology to further secure the encrypted database could be an interesting avenue for future work. By storing the encrypted data on a blockchain network, the security and integrity of the data could be further enhanced, and the risk of data tampering or manipulation could be reduced.


## Conclusion
In our proposed system, we generate an encryption key based on the facial features of a user and a user-provided string input. We store the facial encodings generated from the facial features in the database, but we do not store the entire encryption key.

When the user wants to decrypt the data, they provide a secret string input, which we combine with the stored facial encodings to generate a new encryption key. If we were to store the entire encryption key, including the user-provided string input, this would cause an issue during decryption. Specifically, when the user enters the secret string, the system would append the facial encodings and encryption key of the secret string twice, resulting in an invalid encryption key.

To avoid this issue, we only store the facial encodings in the database, and generate the encryption key using both the stored facial encodings and the user-provided secret string input during decryption. This approach ensures that the encryption key is never stored in its entirety in the database, providing an additional layer of security against potential attacks.
