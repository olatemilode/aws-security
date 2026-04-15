# Essay on the given scenario of a company that uses one AWS root account for daily operations

This given scenario highlights secutrity veulnerabilities. The practices expose the organization to severe risks such as data breaches, unauthorized access and loss of control over infrastructure.
A root account has full, unrestricted access to all AWS services and resources. If compromised, attacker would gain complete control over the environment, potentially leaing to data loss, finnacial damage or service disruption.
Allowing SSH access from anywhere (0.0.0.0/0) exposes servers to the entire internet. This makes the system vulnerable to:
- Brute-force attacks
- Unauthourize login attempts 
- Automated bots scanning  for open ports
Storing backups in s3 without proper access control is a major risk. Without restrictions sensitive data could be publicly accessible and also compliance requirements may be violated.

# Best Practices to solve the risk
To improve security, the company should ensure users only have access to what they need. The root account should only be use for critical tasks, Enable MFA (Multi-factor authentication) and regularly auit permissions and activity logs.

# Using IAM, Roles and Security Groups
AWS Identity and Access Management (IAM) should be the founation of any secure AWS environment. The root account should only be used for initial account setup and billing management, with multi-factor authentication enabled.
Each teams should have their own individual IAM user with the minimum permissions required to perform their job (a principle known as least privilege).A developer should only have access to development resources, while database administrator only have access to database services. 
Security groups act as virtual firewalls. Only open necessary ports (principle of minimal exposure).

# Securing SSH access 
SSH should be tightly controlled, Key based authentication should be used instead of passwords.
Restricting access to specific IP addresses also secure SSH, and also rotate SSH keys regularly.

# Controlling S3 access
S3 buckets should never be publicly accessible. Block public access settings shoul be turnesd on at both the account and bucket level. Bucket policies should explicitly define which IAM roles or users can read, write or delete objects. Server-site encryption should be enabled to protect data at rest, and aslo S3 versioning should be enabled to protect against accidental deletion. Access logs shoul be enabled to track who accessed what and when.


# Conclusion 
The original setup exposes the company to serious security threats due to poor identity management, unrestricted network access, and lack of data protection. By implementing IAM best practices, restricting SSH access, securing S3 storage and properly configurating security groups, teh organixation can significantly strengthen its security posture. 
Adopting all these measures did not only protects critical resources but also ensures compliance, accountability and long term operational stability in teh cloud. 