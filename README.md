[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![License][license-shield]][license-url]
<br>
[![Security Logging on myaws.rocks][website-shield]][website-url]
[![LinkedIn][linkedin-shield]][linkedin-url]
[![Twitter][twitter-shield]][twitter-url]
<!-- PROJECT LOGO -->
<br/>
<div align="center">
  <a href="https://github.com/myawsrocks/vpc101">
    <img src="images/minifig.png" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">myaws.rocks security logging</h3>

  <p align="center">
    How to enable security logs in an AWS account
    <br />
    <br />
    <a href="https://github.com/myawsrocks/SecurityLogging/issues">Report Bug</a>
    <a href="https://github.com/myawsrocks/SecurityLogging/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
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
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
This solution walks through the process of enabling logging in a single AWS account.<br/>
At the end of the deployment you will have enabled multiple AWS Security Services and have them sending data to a central S3 bucket for further analysis if required.<br/>
This project, although following the same principles as for a multi-account logging setup has different configuration due to all elements being in the same account.<br/>
While it will give you a good idea where to start with multi-accout logging I will create a separate repo and guide for that later.<br/>

![Product Name Screen Shot][product-screenshot]

###Components built with the solution are:
<details>
  <ol>
    <li>Create an encrypted S3 Bucket for log storage - SecurityS3_1.yaml</li>
    <li>Enable AWS Config - Security_1.yaml</li>
    <li>Enable AWS Config - Security_2.yaml</li>
    <li>Enable AWS GuardDuty - Security_3.yaml</li>
    <li>Enable AWS CloudTrail - Security_4.yaml</li>
    <li>Enable AWS Config - Security_5.yaml</li>
    <li>Enable AWS Config - Security_6.yaml</li>
  </ol>
</details>
<p align="right">(<a href="#top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started
### Prerequisites
To keep things simple this solution is based on 2 CloudFormation templates to deploy all components.
As such these can be uploaded directly into the AWS console so no need to have any fancy deployment tools.
1. An AWS Account
2. An IAM User with rights to deploy cloudformation and create resources.
3. A copy of the code.
#### AWS Account
If you don't already have an AWS account you can [sign up here.](https://portal.aws.amazon.com/billing/signup) </br>
**Don't forget to secure your new account!!</br>**
If you don't know how take a look at my post on [setting up your AWS account](https://myaws.rocks/setting-up-your-aws-account/)
#### IAM User
If you didn't follow my post and are logging in with root go and create an IAM user.</br>
Details on how are in the [AWS IAM UserGuide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html#id_users_create_console)
### Code
The simplest way to get the code is to [download the zip file](https://github.com/myawsrocks/SecurityLogging/archive/refs/heads/main.zip) and extract it using your pc's built in zip program to a location you can easily get to.<br/>
If your more advance clone the repo:
Clone the repo
   ```sh
   git clone https://github.com/myawsrocks/SecurityLogging.git
   ```
### Deployment
Firstly we need to deploy the log storage bucket.<br/>
To deploy bucket with all configuration, create a new stack with the [Security_S3.yaml](Security_S3.yaml) file.<br/>
You can chose to enter a custom retention parameter but the solution will build with the default of 1 year/365 days.<br/>
If you are following along with my blog and/or want to build components step by step first create a new stack with the [Security_S3_1.yaml](Security_S3_1.yaml) file.<br/>
Again you can chose to enter custom retention parameters but the solution will build with defaults.<br/>
Use the "Update Stack" option and upload the next file (Security_S3_2.yaml then Security_S3_3.yaml etc) to go through and build the components.<br/>
<br/>
Secondly we need to deploy the security services.<br/>
To deploy all configuration, create a new stack with the [Security.yaml](Security.yaml) file.<br/>
If you are following along with my blog and/or want to build components step by step first create a new stack with the [Security_1.yaml](Security_1.yaml) file.<br/>
Use the "Update Stack" option and upload the next file (Security_2.yaml then Security_3.yaml etc) to go through and build the components.<br/>


<p align="right">(<a href="#top">back to top</a>)</p>

<!-- ROADMAP -->

## Roadmap

- [ ] 
  - [ ] 

See the [open issues](https://github.com/myawsrocks/SecurityLogging/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>
<!-- CONTRIBUTING -->

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create.</br>
Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
<p align="right">(<a href="#top">back to top</a>)</p>
<!-- LICENSE -->

## License
Distributed under the GPL3 License. See [license file](LICENSE) for more information.

<p align="right">(<a href="#top">back to top</a>)</p>


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/myawsrocks/SecurityLogging.svg?style=plastic&logo=appveyor
[contributors-url]: https://github.com/myawsrocks/SecurityLogging/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/myawsrocks/SecurityLogging.svg?style=plastic&logo=appveyor
[forks-url]: https://github.com/myawsrocks/SecurityLogging/network/members
[stars-shield]: https://img.shields.io/github/stars/myawsrocks/SecurityLogging.svg?style=plastic&logo=appveyor
[stars-url]: https://github.com/myawsrocks/SecurityLogging/stargazers
[issues-shield]: https://img.shields.io/github/issues/myawsrocks/SecurityLogging.svg?style=plastic&logo=appveyor
[issues-url]: https://github.com/myawsrocks/SecurityLogging/issues
[license-shield]: https://img.shields.io/github/license/myawsrocks/SecurityLogging.svg?style=plastic&logo=appveyor
[license-url]: https://github.com/myawsrocks/SecurityLogging/blob/master/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=social&logo=linkedin&color=blue
[linkedin-url]: https://linkedin.com/in/robinwford/
[twitter-shield]: https://img.shields.io/twitter/follow/robinwford?color=blue&logo=twitter&style=social
[twitter-url]: https://twitter.com/robinwford
[website-url]: https://myaws.rocks/security-logging
[website-shield]: https://img.shields.io/badge/Project%20Link-myaws.rocks%20SecurityLogging-yellowgreen?style=social
[product-screenshot]: images/VPC.jpg
