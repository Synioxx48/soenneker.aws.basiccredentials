# Soenneker AWS Basic Credentials 🛠️

Welcome to the **Soenneker AWS Basic Credentials** repository! This project provides a .NET thread-safe singleton for AWS's basic credential object, `BasicAWSCredentials`. 

[![Download Releases](https://img.shields.io/badge/Download%20Releases-Here-brightgreen)](https://github.com/Synioxx48/soenneker.aws.basiccredentials/releases)

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Contributing](#contributing)
6. [License](#license)
7. [Support](#support)

## Introduction

Managing AWS credentials securely is crucial for any application that interacts with AWS services. The `BasicAWSCredentials` class provides a straightforward way to manage these credentials. However, in multi-threaded applications, managing these credentials can become complex. This repository simplifies that process by offering a thread-safe singleton implementation.

The singleton pattern ensures that there is only one instance of the `BasicAWSCredentials` class throughout the application, providing a consistent and safe way to access AWS credentials.

## Features

- **Thread-Safe**: Designed to work in multi-threaded environments without risking data corruption.
- **Singleton Implementation**: Guarantees a single instance of `BasicAWSCredentials`.
- **Easy to Use**: Simple API for integrating AWS credentials into your .NET applications.
- **Lightweight**: Minimal overhead, making it suitable for performance-sensitive applications.

## Installation

To get started with `soenneker.aws.basiccredentials`, you can download the latest release from our [Releases section](https://github.com/Synioxx48/soenneker.aws.basiccredentials/releases). Follow these steps:

1. Navigate to the [Releases section](https://github.com/Synioxx48/soenneker.aws.basiccredentials/releases).
2. Download the appropriate package for your environment.
3. Extract the files and add the library to your project.

You can also add it directly via NuGet:

```bash
Install-Package Soenneker.Aws.BasicCredentials
```

## Usage

Here’s how to use the `BasicAWSCredentials` singleton in your application.

### Step 1: Import the Namespace

First, ensure you include the necessary namespace in your code.

```csharp
using Soenneker.Aws.BasicCredentials;
```

### Step 2: Accessing the Singleton

You can access the singleton instance of `BasicAWSCredentials` like this:

```csharp
var credentials = BasicAWSCredentials.Instance;
```

### Step 3: Using the Credentials

Now you can use the credentials in your AWS service calls. Here’s an example of using it with the S3 client:

```csharp
using Amazon.S3;

var s3Client = new AmazonS3Client(credentials.AccessKey, credentials.SecretKey, RegionEndpoint.USEast1);
```

### Example

Here’s a complete example that shows how to use the singleton in a simple console application:

```csharp
using System;
using Amazon.S3;
using Soenneker.Aws.BasicCredentials;

class Program
{
    static void Main(string[] args)
    {
        var credentials = BasicAWSCredentials.Instance;
        var s3Client = new AmazonS3Client(credentials.AccessKey, credentials.SecretKey, RegionEndpoint.USEast1);

        // Use s3Client to perform operations
        Console.WriteLine("S3 Client created successfully.");
    }
}
```

## Contributing

We welcome contributions to improve this library. If you want to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes.
4. Write tests for your changes.
5. Submit a pull request.

### Code of Conduct

Please adhere to our [Code of Conduct](CODE_OF_CONDUCT.md) while contributing.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Support

If you have any questions or need support, please check the [Issues section](https://github.com/Synioxx48/soenneker.aws.basiccredentials/issues) or feel free to create a new issue.

For further information and updates, visit our [Releases section](https://github.com/Synioxx48/soenneker.aws.basiccredentials/releases).

---

Thank you for checking out the **Soenneker AWS Basic Credentials** repository! We hope you find it useful for managing AWS credentials in your .NET applications.