# Readings: API Deployment

Below you will find some reading material, code samples, and some additional resources that support today’s topic and the upcoming lecture.

Review the Submission Instructions for guidance on completing and submitting this assignment.

## Reading

[Django Settings Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)
Managing Django Settings: issues
Usually you'll have serveral environments; local, dev, ci, qa, staging, production and more
Each environment can have it's own specific settings. 
You'll need to approach that allows you to keep all these django setting configuations 

You also have sensitive data such as your SECRET_KEY in your django project. 
You may also  have DB passwords and tokens for APIs. 

There are a few approachs
You could have a local_settings.py and a settings.py
you could have a settings package that has base.py, ci.py, local.py, qa.py etc. 
or you could set up an ENV file which is what we've done in the past. 

#### Django Settings: Best practices
-   Keep settings in environment variables.
-   Write default values for production configuration (excluding secret keys and tokens).
-   Don’t hardcode sensitive settings, and don’t put them in VCS.
-   Split settings into groups: Django, third-party, project.
-   Follow naming conventions for custom (project) settings.


#### Conclusion 
Setting file is a small but very important part of any django project, if you do it wrong you'll have a lot of issues during all phases of development. 
By using the environmental variables approach you can easily switch from a monolith to microservice architecture, wrap your project in a docker container, and deploy it. 


[SSH Tutorial](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work)

What is SSH? Secure Shell Protocol: a remote administration protocol allowing users to access, control and modify their remote servers over the internet.

If you're using Linux or Mac this is easy, surprise :P 
If you're using windows you'll need to utilize a SSH client to open SSH connections. Most popular is PuTTY

Different Encryption Techniques:
1.  Symmetrical encryption
	1. A secret key is used for both encryption and decryption.  Effectively, anyone possessing the key can decrypt the message being transferred.
	2. ![Symetirical Encryption](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/symmetric-encryption-ssh-tutorial.webp)
2.  Asymmetrical encryption
	1. Uses two separate keys for encryption and decryption. Together both keys form a public-private key pair
	2. ![Asymmetrical Encryption](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/asymmetric-encryption.webp)
3.  Hashing
	1.  This is never meant to be decrypted. Generate a unique value of a fixed length for each input that shows no clear trend. Practically impossible to reverse.
	2. ![Hashing](https://www.hostinger.com/tutorials/wp-content/uploads/sites/2/2017/07/ssh-tutorial-hash.webp)

How the algorithm works on a very basic level:
1. Both client and server agree on a large prime number. Prime number is called the seed value
2. Two parties agree on a common encryption mechanism to generate another set of values by manipulating the seed values. 
3. Both parties independently generate another prime number, used as a secret private key for interaction
4. Newly generated private key is used to compute a public key distributed to the other computer
5. Parties use their personal private key, and the public key, as well as the original prime number to create a final shared key. This key is independently computed by both computers but will create the same encryption key on both sides. 
6. Now they can synmetrically encrypt the entire SSH session. 

## Bookmark and Review

[White Noise](http://whitenoise.evans.io/en/stable/)

[IaaS](https://en.wikipedia.org/wiki/Infrastructure_as_a_service)

[PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service)

[CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)