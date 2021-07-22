# Azure Compute

Azure compute is an on-demand computing service for running cloud-based applications. It provides computing resources such as dkisk, processors, memory, networking and operationg systems. The resources are available on-demand and can typically be made available in minutes or even seconds. You pay only for the resources you use, and only for as long you're using them.

Most prominent services are:

- Azure Virtual Machines
    Virtual machine scale sets, are an Azure compute resource that you can use to deploy and manage a set of identical VMs. Support autoscaling.
- Azure Container Instances
    Containers Instances and AKS Azure Kubernetes services are Azure compute resources that you can use to deploy and manage containers.
- Azure App Service
    You can quickly build, deploy and scale enterprise-grede web, mobile and API apps running on any platform.
- Azure Functions (or serverless computing)
    Are ideal when you're concerned only about the code running your service and not the underlying platform or infrastructure.. Commonly used whn you need to perform work in response to an event (often via a REST request), timer, or message from another Azure service.

## Azure Virtual Machines

With Azure Virtual Machines, you can create and use VMs in the cloud. VMs provide infrastructure as a service (IaaS) in the form of a virtualized server and can be used in many ways. Just like a physical computer, you can customize all of the software running on the VM. VMs are an ideal choice when you need:

Total control over the operating system (OS).
The ability to run custom software.
To use custom hosting configurations.

## App Service

App Service enables you to build and host web apps, background jobs, mobile back-ends, and RESTful APIs in the programming language of your choice without managing infrastructure. It offers automatic scaling and high availability. App Service supports Windows and Linux and enables automated deployments from GitHub, Azure DevOps, or any Git repo to support a continuous deployment model.

With App Service, you can host most common app service styles like:

- Web apps (ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP, or Python. You can choose either Windows or Linux as the host operating system.)
- API apps (can build REST-based web APIs by using your choice of language and framework. You get full Swagger support and the ability to package and publish your API in Azure Marketplace. The produced apps can be consumed from any HTTP- or HTTPS-based client.)
- WebJobs (You can use the WebJobs feature to run a program (.exe, Java, PHP, Python, or Node.js) or script (.cmd, .bat, PowerShell, or Bash) in the same context as a web app, API app, or mobile app. They can be scheduled or run by a trigger. WebJobs are often used to run background tasks as part of your application logic)
- Mobile apps (Use the Mobile Apps feature of App Service to quickly build a back end for iOS and Android apps. With just a few clicks in the Azure portal, you can: Store mobile app data in a cloud-based SQL DB, Authenticate customers against common social providers, such as MSA, Google, Twitter and Facebook, Send push notifications, Execute custom back-end logic in C# or Node.js. On the mobile app side, there's SDK support for native iOS and Android, Xamarin and React native apps.

App Service handles most of the infrastructure decisions you deal with in hosting web-accessible apps:

Deployment and management are integrated into the platform.
Endpoints can be secured.
Sites can be scaled quickly to handle high traffic loads.
The built-in load balancing and traffic manager provide high availability.
All of these app styles are hosted in the same infrastructure and share these benefits. This flexibility makes App Service the ideal choice to host web-oriented applications.

## Containers

- Azure Container Instances
- Azure Kuberneteds Service

Microservices (simplify an application architecture by focusing on create smaller, more maneagable, automomous and independen deploy web services that addresses a single business domain or capability)

Provide a layer of fault isolation.
Microservices can communicate by APIs
Large app High release velocity
Complex apps Highly scalable
Apps with Rich domains
Organization consists on small development teams

## Azure Functions

For applications on where it's logic is event driven. In other words, for a large amount of time, your application is waiting for a particular input before it performs any processing. To reduce your costs, you want to avoid having to pay for the time that your application is waiting for input.

- Azure Functions: Functions can execute code in almost any modern language.
- Azure Logic Apps: Logic apps are designed in a web-based designer and can execute logic triggered by Azure services without writing any code.
