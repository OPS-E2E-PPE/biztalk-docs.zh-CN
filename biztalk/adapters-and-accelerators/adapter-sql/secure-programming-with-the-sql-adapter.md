---
title: 使用 SQL 适配器的安全编程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e0c5e68eb1f07067a43995693cbb43bdcad76a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002382"
---
# <a name="secure-programming-with-the-sql-adapter"></a><span data-ttu-id="9d334-102">使用 SQL 适配器进行安全编程</span><span class="sxs-lookup"><span data-stu-id="9d334-102">Secure programming with the SQL adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="9d334-103">在使用时如何保护凭据添加适配器服务参考 Visual Studio 插件？</span><span class="sxs-lookup"><span data-stu-id="9d334-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="9d334-104">当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，您可能需要提供用户名和密码的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="9d334-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you might have to supply a user name and password for the SQL Server database.</span></span> <span data-ttu-id="9d334-105">必须输入的凭据**安全**选项卡上**配置适配器**对话框。</span><span class="sxs-lookup"><span data-stu-id="9d334-105">You must enter credentials from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="9d334-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不提供一个选项以指定的用户名和密码连接 URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9d334-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not provide an option to specify the user name and password as part of the connection URI.</span></span> <span data-ttu-id="9d334-107">这可确保：</span><span class="sxs-lookup"><span data-stu-id="9d334-107">This ensures the following:</span></span>  
  
- <span data-ttu-id="9d334-108">凭据不会显示在**配置 URI**字段**添加适配器服务引用插件**有权访问您的计算机屏幕的任何人都可以读取的对话框。</span><span class="sxs-lookup"><span data-stu-id="9d334-108">The credentials will not be displayed in the **Configure a URI** field of the **Add Adapter Service Reference Plug-in** dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="9d334-109">凭据不会出现在配置文件的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="9d334-109">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="9d334-110">详细了解如何使用生成 WCF 客户端[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何为 SQL Server 数据库中输入用户名和密码，请参阅[获取 Visual Studio 中使用 SQL 适配器中的SQLServer操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="9d334-110">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the SQL Server database, see [Get metadata for SQL Server operations in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="9d334-111">在代码中设置凭据的最佳做法是什么？</span><span class="sxs-lookup"><span data-stu-id="9d334-111">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="9d334-112"> 提供了**ClientCredentials**类来帮助你配置客户端通信对象，例如凭据**ChannelFactory**，用于验证自己身份的服务。</span><span class="sxs-lookup"><span data-stu-id="9d334-112"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="9d334-113">通过使用**ClientCredentials**类中，确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。</span><span class="sxs-lookup"><span data-stu-id="9d334-113">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="9d334-114">因为[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]托管在其使用方应用程序的进程，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。</span><span class="sxs-lookup"><span data-stu-id="9d334-114">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="9d334-115">但是，认为是很好的做法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9d334-115">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="9d334-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]需要使用**ClientCredentials**类以编程方式传递凭据。</span><span class="sxs-lookup"><span data-stu-id="9d334-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the use of the **ClientCredentials** class for programmatically passing credentials.</span></span> <span data-ttu-id="9d334-117">**AcceptCredentialsInUri**绑定属性将被忽略[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以防止在 URI 中的传递凭据。</span><span class="sxs-lookup"><span data-stu-id="9d334-117">The **AcceptCredentialsInUri** binding property is ignored by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to prevent passing credentials in the URI.</span></span>  
  
 <span data-ttu-id="9d334-118">下面的示例演示如何使用**凭据**属性上设置 SQL Server 数据库的凭据**ChannelFactory**。</span><span class="sxs-lookup"><span data-stu-id="9d334-118">The following example shows how to use the **Credentials** property to set credentials for the SQL Server database on a **ChannelFactory**.</span></span>  
  
```  
// Create binding and endpoint  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 <span data-ttu-id="9d334-119">下面的示例演示如何使用**ClientCredentials**类在 WCF 客户端上设置 SQL Server 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="9d334-119">The following example shows how to use the **ClientCredentials** class to set credentials for the SQL Server database on a WCF client.</span></span>  
  
```  
// Initialize a new client for the SELECT operation on the Employee table   
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient(binding,address);  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="9d334-120">如何提供更安全的数据交换跨进程边界？</span><span class="sxs-lookup"><span data-stu-id="9d334-120">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="9d334-121">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]托管进程的应用程序或服务，使用它。</span><span class="sxs-lookup"><span data-stu-id="9d334-121">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="9d334-122">因为适配器的宿主的进程中使用者，则无需使用者之间交换的消息上提供的安全性和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9d334-122">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="9d334-123">但是，如果使用的应用程序或服务发送消息的跨进程边界到另一个服务或客户端包含敏感的数据库的信息，应采取措施来提供充分的保护环境中的此数据。</span><span class="sxs-lookup"><span data-stu-id="9d334-123">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="9d334-124"> 提供了多种用来帮助来保护客户端和服务之间发送的消息。</span><span class="sxs-lookup"><span data-stu-id="9d334-124"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="9d334-125">有关帮助来保护客户端和服务之间发送的消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9d334-125">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="9d334-126">有关更多常规信息安全功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9d334-126">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d334-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d334-127">See Also</span></span>  
[<span data-ttu-id="9d334-128">保护 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="9d334-128">Secure your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[<span data-ttu-id="9d334-129">最佳做法来保护 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="9d334-129">Best practices to secure the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)