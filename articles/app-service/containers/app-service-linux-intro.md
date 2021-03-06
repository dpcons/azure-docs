---
title: Introduction to App Service on Linux | Microsoft Docs
description: Learn about Azure App Service on Linux.
keywords: azure app service, linux, oss
services: app-service
documentationcenter: ''
author: naziml
manager: cfowler
editor: ''

ms.assetid: bc85eff6-bbdf-410a-93dc-0f1222796676
ms.service: app-service
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: overview
ms.date: 02/16/2017
ms.author: wesmc
ms.custom: mvc

---
# Introduction to Azure App Service on Linux

[Web App](../app-service-web-overview.md) is a fully managed compute platform that is optimized for hosting websites and web applications. Customers can use App Service on Linux to host web apps natively on Linux for supported application stacks. The following sections lists the application stacks that are currently supported.

## Languages

App Service on Linux supports a number of Built-in images in order to increase developer productivity. If the runtime your application requires is not supported in the built-in images, there are instructions on how to [build your own Docker image](tutorial-custom-docker-image.md) to deploy to Web App for Containers.

| Language | Supported Versions |
|---|---|
| Node.js | 4.4, 4.5, 6.2, 6.6, 6.9-6.11, 8.0, 8.1 |
| Java * | 8.0 |
| PHP | 5.6, 7.0 |
| .NET Core | 1.0, 1.1, 2.0 |
| Ruby | 2.3 |

* Preview feature support

### Preview: supported Java runtimes

Java runtimes available on App Service on Linux are the following:

| Runtime | Version |
|---|---|
| Apache Tomcat | 8.5 |
| Apache Tomcat | 9.0 |

See [Create a Java web app in App Service on Linux](https://docs.microsoft.com/en-us/azure/app-service/containers/quickstart-java) for more details.

## Deployments

* FTP
* Local Git
* GitHub
* Bitbucket

## DevOps

* Staging environments
* [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/container-registry-intro) and DockerHub CI/CD

## Console, Publishing, and Debugging

* Environments
* Deployments
* Basic console
* SSH

## Scaling

* Customers can scale web apps up and down by changing the tier of their [App Service plan](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview?toc=%2fazure%2fapp-service-web%2ftoc.json)

## Locations

Check the [Azure Status Dashboard](https://azure.microsoft.com/status).

## Limitations

The Azure portal shows only features that currently work for Web App for Containers. As we enable more features, they will become visible on the portal.

Some features, such as virtual network integration, Azure Active Directory/third-party authentication, or Kudu site extensions, are not available yet. Once these features are available, we will update our documentation and blog about the changes.

App Service on Linux is only supported with [Basic and Standard](https://azure.microsoft.com/pricing/details/app-service/plans/) app service plans and does not have a [Free or Shared](https://azure.microsoft.com/pricing/details/app-service/plans/) tier. The following are also important restrictions for App Service on Linux:

* You cannot create Web App for Containers in an App Service plan already hosting non-Linux Web Apps.
* When creating Web App for Containers in a resource group containing non-Linux Web Apps, you must create an App Service plan in a different resource group than the existing App Service plan.

## Troubleshooting

When your application fails to start or you want to check the logging from your app, check the Docker logs in the LogFiles directory. You can access this directory either through your SCM site or via FTP.
To log the `stdout` and `stderr` from your container, you need to enable **Docker Container logging** under **Diagnostics Logs**.

![Enabling Logging][2]

![Using Kudu to view Docker logs][1]

You can access the SCM site from **Advanced Tools** in the **Development Tools** menu.

## Next steps

See the following links to get started with App Service on Linux. You can post questions and concerns on [our forum](https://social.msdn.microsoft.com/forums/azure/home?forum=windowsazurewebsitespreview).

* [How to use a custom Docker image for Web App for Containers](quickstart-docker-go.md)
* [Using .NET Core in Azure App Service on Linux](quickstart-dotnetcore.md)
* [Using Ruby in Azure App Service on Linux](quickstart-ruby.md)
* [Azure App Service Web App for Containers FAQ](app-service-linux-faq.md)
* [SSH support for Azure App Service on Linux](app-service-linux-ssh-support.md)
* [Set up staging environments in Azure App Service](../../app-service/web-sites-staged-publishing.md?toc=%2fazure%2fapp-service%2fcontainers%2ftoc.json)
* [Docker Hub Continuous Deployment with Web App for Containers](./app-service-linux-ci-cd.md)

<!--Image references-->
[1]: ./media/app-service-linux-intro/kudu-docker-logs.png
[2]: ./media/app-service-linux-intro/logging.png
