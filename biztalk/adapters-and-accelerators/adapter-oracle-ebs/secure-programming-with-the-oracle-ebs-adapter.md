---
title: 安全使用 Oracle EBS 适配器编程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b494f8-cb21-45c2-9bb4-097ba59ec52c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd42207ce96cd322f37fa75cc6fdd0f38727c634
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374597"
---
# <a name="secure-programming-with-the-oracle-ebs-adapter"></a><span data-ttu-id="32c51-102">使用 Oracle EBS 适配器进行安全编程</span><span class="sxs-lookup"><span data-stu-id="32c51-102">Secure programming with the Oracle EBS adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="32c51-103">在使用时如何保护凭据添加适配器服务参考 Visual Studio 插件？</span><span class="sxs-lookup"><span data-stu-id="32c51-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="32c51-104">当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，但是您必须提供用户名和密码用于 Oracle E-business Suite。</span><span class="sxs-lookup"><span data-stu-id="32c51-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the Oracle E-Business Suite.</span></span> <span data-ttu-id="32c51-105">您应仅执行此操作从**安全**选项卡上**配置适配器**对话框。</span><span class="sxs-lookup"><span data-stu-id="32c51-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="32c51-106">通过输入 Oracle 凭据**安全**选项卡而不是直接**配置 URI**字段中，您可以确保以下：</span><span class="sxs-lookup"><span data-stu-id="32c51-106">By entering the Oracle credentials from the **Security** tab instead of directly into the **Configure a URI** field, you ensure the following:</span></span>  
  
- <span data-ttu-id="32c51-107">凭据不会显示在**配置 URI**字段[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]有权访问您的计算机屏幕的任何人都可以读取的对话框。</span><span class="sxs-lookup"><span data-stu-id="32c51-107">The credentials will not be displayed in the **Configure a URI** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="32c51-108">凭据不会出现在配置文件的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="32c51-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="32c51-109">详细了解如何使用生成 WCF 客户端[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何为 Oracle E-business Suite 中输入用户名和密码，请参阅[获取 Visual Studio中的OracleE-businessSuite操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="32c51-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the Oracle E-Business Suite, see [Get metadata for Oracle E-Business Suite operations in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="32c51-110">在代码中设置凭据的最佳做法是什么？</span><span class="sxs-lookup"><span data-stu-id="32c51-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] <span data-ttu-id="32c51-111">提供了**ClientCredentials**类来帮助你配置客户端通信对象，例如凭据**ChannelFactory**，用于验证自己身份的服务。</span><span class="sxs-lookup"><span data-stu-id="32c51-111">provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="32c51-112">通过使用**ClientCredentials**类中，确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。</span><span class="sxs-lookup"><span data-stu-id="32c51-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="32c51-113">因为[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]托管在其使用方应用程序的进程，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。</span><span class="sxs-lookup"><span data-stu-id="32c51-113">Because the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="32c51-114">但是，认为是很好的做法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="32c51-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="32c51-115">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]鼓励使用**ClientCredentials**类。</span><span class="sxs-lookup"><span data-stu-id="32c51-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] encourages the use of the **ClientCredentials** class.</span></span> <span data-ttu-id="32c51-116">此属性指定适配器将接受的用户名和密码连接 URI 中的 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="32c51-116">This property specifies whether the adapter will accept the user name and password for the Oracle database in the connection URI.</span></span> <span data-ttu-id="32c51-117">**AcceptCredentialsInUri**默认情况下**false**，这意味着，如果连接 URI 中包含的凭据，适配器将引发异常。</span><span class="sxs-lookup"><span data-stu-id="32c51-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="32c51-118">可以设置**AcceptCredentialsInUri**到**true**中提供凭据的连接 URI，如果需要在客户端应用程序中。</span><span class="sxs-lookup"><span data-stu-id="32c51-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI, if required in the client application.</span></span>  
  
 <span data-ttu-id="32c51-119">下面的示例演示如何使用**凭据**属性上设置 Oracle E-business Suite 凭据**ChannelFactory**。</span><span class="sxs-lookup"><span data-stu-id="32c51-119">The following example shows how to use the **Credentials** property to set credentials for the Oracle E-Business Suite on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
OracleEBSBinding binding = new OracleEBSBinding();  
EndpointAddress address = new EndpointAddress("oracleebs://ebs-instance");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="32c51-120">下面的示例演示如何使用**ClientCredentials**类设置的 Oracle E-business Suite 的 WCF 客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="32c51-120">The following example shows how to use the **ClientCredentials** class to set credentials for the Oracle E-Business Suite on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
ConcurrentPrograms_ARClient client =   
  new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="32c51-121">如何提供更安全的数据交换跨进程边界？</span><span class="sxs-lookup"><span data-stu-id="32c51-121">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="32c51-122">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]托管进程的应用程序或服务，使用它。</span><span class="sxs-lookup"><span data-stu-id="32c51-122">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="32c51-123">因为适配器的宿主的进程中使用者，则无需使用者之间交换的消息上提供的安全性和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="32c51-123">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="32c51-124">但是，如果使用的应用程序或服务发送消息的跨进程边界到另一个服务或客户端包含敏感的数据库的信息，应采取措施来提供充分的保护环境中的此数据。</span><span class="sxs-lookup"><span data-stu-id="32c51-124">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] <span data-ttu-id="32c51-125">提供了多种用来帮助来保护客户端和服务之间发送的消息。</span><span class="sxs-lookup"><span data-stu-id="32c51-125">provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="32c51-126">有关帮助来保护客户端和服务之间发送的消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅"保护服务和客户端"，网址[ http://go.microsoft.com/fwlink/?LinkId=89725 ](http://go.microsoft.com/fwlink/?LinkId=89725)。</span><span class="sxs-lookup"><span data-stu-id="32c51-126">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see "Securing Services and Clients" at [http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725).</span></span> <span data-ttu-id="32c51-127">有关更多常规信息安全功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅"Windows Communication Foundation 安全"，网址[ http://go.microsoft.com/fwlink/?LinkId=89726 ](http://go.microsoft.com/fwlink/?LinkId=89726)。</span><span class="sxs-lookup"><span data-stu-id="32c51-127">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see "Windows Communication Foundation Security" at [http://go.microsoft.com/fwlink/?LinkId=89726](http://go.microsoft.com/fwlink/?LinkId=89726).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c51-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="32c51-128">See Also</span></span>  
 [<span data-ttu-id="32c51-129">保护 Oracle EBS 应用程序</span><span class="sxs-lookup"><span data-stu-id="32c51-129">Secure your Oracle EBS applications</span></span>](secure-your-oracle-ebs-applications.md)