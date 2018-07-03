---
title: 使用 SAP 适配器的安全编程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, considerations when programming on the adapter
- security, secure data exchange
- security, setting credentials in code
ms.assetid: bd5da271-90f1-4a64-9138-a51048a16648
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7fbdd561c739e6312ca1300bc9b886afdee5376
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015702"
---
# <a name="secure-programming-with-the-sap-adapter"></a><span data-ttu-id="d17bd-102">使用 SAP 适配器进行安全编程</span><span class="sxs-lookup"><span data-stu-id="d17bd-102">Secure programming with the SAP adapter</span></span>
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a><span data-ttu-id="d17bd-103">在使用时如何保护凭据添加适配器服务参考 Visual Studio 插件？</span><span class="sxs-lookup"><span data-stu-id="d17bd-103">How Do I Protect Credentials When I Use the Add Adapter Service Reference Visual Studio Plug-in?</span></span>  
 <span data-ttu-id="d17bd-104">当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]若要创建 WCF 客户端，必须提供用户名和密码为 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="d17bd-104">When you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to create a WCF client, you must supply a user name and password for the SAP system.</span></span> <span data-ttu-id="d17bd-105">您应仅执行此操作从**安全**选项卡上**配置适配器**对话框。</span><span class="sxs-lookup"><span data-stu-id="d17bd-105">You should only do this from the **Security** tab on the **Configure Adapter** dialog box.</span></span> <span data-ttu-id="d17bd-106">通过输入 SAP 凭据**安全**选项卡而不是直接**Uri**字段中，您可以确保以下：</span><span class="sxs-lookup"><span data-stu-id="d17bd-106">By entering the SAP credentials from the **Security** tab instead of directly into the **Uri** field, you ensure the following:</span></span>  
  
- <span data-ttu-id="d17bd-107">凭据不会显示在**Uri**字段[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]有权访问您的计算机屏幕的任何人都可以读取的对话框。</span><span class="sxs-lookup"><span data-stu-id="d17bd-107">The credentials will not be displayed in the **Uri** field of the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] dialog box where anyone with access to your computer screen can read them.</span></span>  
  
- <span data-ttu-id="d17bd-108">凭据不会出现在配置文件的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]生成。</span><span class="sxs-lookup"><span data-stu-id="d17bd-108">The credentials will not appear in the configuration file that the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates.</span></span>  
  
  <span data-ttu-id="d17bd-109">详细了解如何使用生成 WCF 客户端[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，包括如何为 SAP 系统中输入用户名和密码，请参阅[获取 Visual Studio 中的 SAP 操作的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="d17bd-109">For more information about how to generate a WCF client by using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], including how to enter a user name and password for the SAP system, see [Get Metadata for SAP Operations in Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)</span></span>  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a><span data-ttu-id="d17bd-110">在代码中设置凭据的最佳做法是什么？</span><span class="sxs-lookup"><span data-stu-id="d17bd-110">What Are Best Practices for Setting Credentials in Code?</span></span>  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]<span data-ttu-id="d17bd-111"> 提供了**ClientCredentials**类来帮助你配置客户端通信对象，例如凭据**ChannelFactory**，用于验证自己身份的服务。</span><span class="sxs-lookup"><span data-stu-id="d17bd-111"> provides the **ClientCredentials** class to help you configure the credentials that a client communication object, such as a **ChannelFactory**, uses to authenticate itself with a service.</span></span> <span data-ttu-id="d17bd-112">通过使用**ClientCredentials**类中，确保 WCF 采用该对象的通道堆栈中指定任何身份验证机制，并将其应用到你的客户端和服务之间的交换。</span><span class="sxs-lookup"><span data-stu-id="d17bd-112">By using the **ClientCredentials** class, you ensure that WCF takes whatever authentication mechanisms are specified in that object’s channel stack and applies them to the exchange between your client and the service.</span></span>  
  
 <span data-ttu-id="d17bd-113">因为[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]托管在其使用方应用程序的进程，没有必要使用**ClientCredentials**类来设置凭据在客户端上使用方应用程序使用的通信对象。</span><span class="sxs-lookup"><span data-stu-id="d17bd-113">Because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is hosted in-process with its consuming application, it is not imperative to use the **ClientCredentials** class to set credentials on the client communication objects that the consuming application uses.</span></span> <span data-ttu-id="d17bd-114">但是，认为是很好的做法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d17bd-114">It is, however, considered good practice to do so.</span></span>  
  
 <span data-ttu-id="d17bd-115">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]鼓励使用**ClientCredentials**类通过**AcceptCredentialsInUri**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="d17bd-115">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] encourages the use of the **ClientCredentials** class through the **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="d17bd-116">此属性指定适配器将接受的用户名和密码连接 URI 中的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="d17bd-116">This property specifies whether the adapter will accept the user name and password for the SAP system in the connection URI.</span></span> <span data-ttu-id="d17bd-117">**AcceptCredentialsInUri**默认情况下**false**，这意味着，如果连接 URI 中包含的凭据，适配器将引发异常。</span><span class="sxs-lookup"><span data-stu-id="d17bd-117">**AcceptCredentialsInUri** defaults to **false**, which means that the adapter will throw an exception if the connection URI contains credentials.</span></span> <span data-ttu-id="d17bd-118">可以设置**AcceptCredentialsInUri**到**true**连接 URI 中提供凭据。</span><span class="sxs-lookup"><span data-stu-id="d17bd-118">You can set **AcceptCredentialsInUri** to **true** to supply credentials in the connection URI.</span></span> <span data-ttu-id="d17bd-119">事实上，您必须执行此操作在某些情况下;例如，当指定连接 URI 的服务主机终结点或用于**IReplyChannel**在入站方案。</span><span class="sxs-lookup"><span data-stu-id="d17bd-119">In fact, you must do this in certain cases; for example, when you specify a connection URI for a service host endpoint or for an **IReplyChannel** in inbound scenarios.</span></span>  
  
 <span data-ttu-id="d17bd-120">下面的示例演示如何使用**ClientCredentials**类来设置 WCF 客户端上的 SAP 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="d17bd-120">The following example shows how to use the **ClientCredentials** class to set credentials for the SAP system on a WCF client.</span></span>  
  
```  
SAPBinding binding = new SAPBinding();  
  
// Set endpoint address  
EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
// Create client and set credentials  
RfcClient rfcClient = new RfcClient(binding, endpointAddress);  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a><span data-ttu-id="d17bd-121">如何提供更安全的数据交换跨进程边界？</span><span class="sxs-lookup"><span data-stu-id="d17bd-121">How Can I Provide for More Secure Data Exchange Across Process Boundaries?</span></span>  
 <span data-ttu-id="d17bd-122">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]托管进程的应用程序或服务，使用它。</span><span class="sxs-lookup"><span data-stu-id="d17bd-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is hosted in-process with the application or service that consumes it.</span></span> <span data-ttu-id="d17bd-123">因为适配器的宿主的进程中使用者，则无需使用者之间交换的消息上提供的安全性和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d17bd-123">Because the adapter is hosted in-process with the consumer, there is no need to provide security on messages exchanged between the consumer and the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="d17bd-124">但是，如果使用的应用程序或服务发送消息的跨进程边界到另一个服务或客户端包含敏感的数据库的信息，应采取措施来提供充分的保护环境中的此数据。</span><span class="sxs-lookup"><span data-stu-id="d17bd-124">However, if the consuming application or service sends messages that contain sensitive database information across a process boundary to another service or client, you should take measures to provide adequate protection for this data in your environment.</span></span> [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="d17bd-125"> 提供了多种用来帮助来保护客户端和服务之间发送的消息。</span><span class="sxs-lookup"><span data-stu-id="d17bd-125"> provides many options for helping to secure messages sent between clients and services.</span></span> <span data-ttu-id="d17bd-126">有关帮助来保护客户端和服务之间发送的消息的详细信息[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，请参阅[保护服务和客户端](https://msdn.microsoft.com/library/ms734736.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d17bd-126">For more information about helping to secure messages sent between clients and services in [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], see [Securing Services and Clients](https://msdn.microsoft.com/library/ms734736.aspx).</span></span> <span data-ttu-id="d17bd-127">有关更多常规信息安全功能[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了，请参阅[Windows Communication Foundation 安全性](https://msdn.microsoft.com/library/ms732362.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d17bd-127">For more general information about security features that [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] provides, see [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17bd-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d17bd-128">See Also</span></span>  
[<span data-ttu-id="d17bd-129">最佳做法来保护 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="d17bd-129">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[<span data-ttu-id="d17bd-130">保护 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="d17bd-130">Secure your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   