---
title: SAP 系统和适配器之间的安全 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca967a375e1d64a7e3f720648fb7eb8ceede98b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372893"
---
# <a name="security-between-the-sap-system-and-the-adapter"></a><span data-ttu-id="4dc3f-102">SAP 系统和适配器之间的安全性</span><span class="sxs-lookup"><span data-stu-id="4dc3f-102">Security between the SAP system and the adapter</span></span>
<span data-ttu-id="4dc3f-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]支持以帮助其与 SAP 服务器之间安全通信的 SAP 安全网络通信 (SNC) 或用户名称密码凭据。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports either SAP Secure Network Communications (SNC) or user name password credentials to help secure communication between it and the SAP server.</span></span> <span data-ttu-id="4dc3f-104">用户名密码凭据仅提供到 SAP 系统; 连接的身份验证它们不提供任何安全性上通过连接交换的数据。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-104">User name password credentials only provide authorization for the connection to the SAP system; they do not provide any security on the data exchanged over the connection.</span></span> <span data-ttu-id="4dc3f-105">不能同时使用 SNC 和用户名称密码凭据。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-105">You cannot use both SNC and user name password credentials simultaneously.</span></span>  
  
## <a name="sap-secure-network-communications"></a><span data-ttu-id="4dc3f-106">SAP 安全网络通信</span><span class="sxs-lookup"><span data-stu-id="4dc3f-106">SAP Secure Network Communications</span></span>  
 <span data-ttu-id="4dc3f-107">安全网络通信 (SNC) 是可帮助提供有关 SAP 客户端和 SAP 应用程序服务器之间交换的数据的应用程序级安全，SAP 系统体系结构中的软件层。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-107">Secure Network Communications (SNC) is a software layer in the SAP system architecture that can help provide application-level security on data exchanged between the SAP client and a SAP application server.</span></span>  
  
 <span data-ttu-id="4dc3f-108">SNC 提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="4dc3f-108">SNC provides the following advantages:</span></span>  
  
- <span data-ttu-id="4dc3f-109">SNC 面向应用程序级的、 端到端的安全。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-109">SNC targets application-level, end-to-end security.</span></span> <span data-ttu-id="4dc3f-110">SNC 有助于保护两个 SNC 受保护的组件 （例如，之间 SAPgui 和 SAP 系统应用程序服务器） 之间的所有通信。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-110">SNC helps secure all communications between two SNC-protected components (for example, between the SAPgui and an SAP System application server).</span></span>  
  
- <span data-ttu-id="4dc3f-111">您可以实现 SAP 系统不直接提供 （如单一登录或将智能卡进行身份验证） 的其他安全功能。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-111">You can implement additional security features that the SAP System does not directly provide (for example, Single Sign-On or the use of smart cards for authentication).</span></span>  
  
- <span data-ttu-id="4dc3f-112">您可以自定义 SNC 实现。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-112">You can customize your SNC implementation.</span></span> <span data-ttu-id="4dc3f-113">可以使用所选的安全产品，并选择你想要使用的算法。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-113">You can use the security product of your choice and choose the algorithms you want to use.</span></span>  
  
- <span data-ttu-id="4dc3f-114">您可以在任何时候更改安全产品，而不会影响 SAP 系统的业务应用程序。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-114">You can change the security product at any time without affecting SAP System business applications.</span></span>  
  
  <span data-ttu-id="4dc3f-115">若要使用 SNC，必须配置 SAP 服务器和运行的客户端[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-115">To use SNC, you must configure both the SAP server and the client running the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="4dc3f-116">在 SAP 服务器上配置安全网络通信 (SNC)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-116">Configure Secure Network Communications (SNC) on the SAP server.</span></span> <span data-ttu-id="4dc3f-117">请参阅 SAP 文档有关的指南。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-117">Refer to the SAP documentation for guidance.</span></span>  
  
- <span data-ttu-id="4dc3f-118">SAP 客户端 Dll 的计算机上和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]安装，您还必须拥有 SNC 相关 Dll 的。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-118">On the computer having the SAP client DLLs and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] installed, you must also have the SNC related DLLs.</span></span> <span data-ttu-id="4dc3f-119">有关这些 Dll 的详细信息，请参阅[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)][必备软件](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-119">For more information about these DLLs, see the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] [software prerequisites](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md).</span></span>  
  
- <span data-ttu-id="4dc3f-120">若要配置适配器以使用 SNC，必须在 SAP 连接 URI 设置 UseSnc 参数。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-120">To configure the adapter to use SNC, you must set the UseSnc parameter in the SAP connection URI.</span></span> <span data-ttu-id="4dc3f-121">有关 SAP 连接 URI 的详细信息，请参阅[配置的 SAP 适配器的连接 URI](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-121">For more information about the SAP connection URI, see [Configure the connection URI for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md).</span></span> <span data-ttu-id="4dc3f-122">此外，必须设置**SncLibrary**并**必须提供 SncPartnerName**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-122">Also, you must set the **SncLibrary** and the **SncPartnerName** binding properties.</span></span> <span data-ttu-id="4dc3f-123">有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-123">For more information about the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
## <a name="user-name-password-credentials"></a><span data-ttu-id="4dc3f-124">用户名密码凭据</span><span class="sxs-lookup"><span data-stu-id="4dc3f-124">User Name Password Credentials</span></span>  
 <span data-ttu-id="4dc3f-125">你可以提供给适配器的连接 URI 中的用户名称密码凭据。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-125">You can supply user name password credentials to the adapter in the connection URI.</span></span> <span data-ttu-id="4dc3f-126">适配器使用这些凭据时打开的连接上的 SAP 系统的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-126">The adapter uses these credentials to authenticate the user on the SAP system when it opens the connection.</span></span> <span data-ttu-id="4dc3f-127">这些凭据提供到 SAP 系统; 连接的身份验证的级别但是，它们不提供消息级或传输级身份验证 （或授权） 的数据通过网络传输。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-127">These credentials provide a level of authorization for the connection to the SAP system; however, they do not provide message-level or transport-level authentication (or authorization) for data traveling across the network.</span></span>  
  
 <span data-ttu-id="4dc3f-128">出于此原因，必须提供一种安全机制来帮助确保适当的授权、 身份验证、 数据隐私和数据适配器与 SAP 系统之间交换的数据完整性级别。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-128">For this reason, you must provide a security mechanism to help ensure appropriate levels of authorization, authentication, data privacy, and data integrity for data exchanges between the adapter and the SAP system.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4dc3f-129">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面**AcceptCredentialsInUri**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-129">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces the **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="4dc3f-130">此属性确定是否在连接 URI 中允许 SAP 系统凭据。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-130">This property determines whether SAP system credentials are permitted in the connection URI.</span></span> <span data-ttu-id="4dc3f-131">默认情况下**AcceptCredentialsInUri**为 false 和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]如果凭据包含在 URI 中将引发异常。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-131">By default, **AcceptCredentialsInUri** is false and the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] throws an exception if credentials are included in the URI.</span></span> <span data-ttu-id="4dc3f-132">有关详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-132">For more information, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
 <span data-ttu-id="4dc3f-133">帮助提供更高的安全性网络上的一个可能的机制是 Internet 协议安全性 (IPsec)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-133">One possible mechanism for helping to provide more security across the network is Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="4dc3f-134">IPsec 是一种开放标准来保护通过 Internet 协议 (IP) 网络的通信框架。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-134">IPsec is a framework of open standards for protecting communications over Internet Protocol (IP) networks.</span></span>  
  
 <span data-ttu-id="4dc3f-135">以明文形式的连接 URI 中指定的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-135">The user name and password are specified as clear text in the connection URI.</span></span> <span data-ttu-id="4dc3f-136">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供了多种方法，通过它可以更安全地提供这些凭据。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-136">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] provides a number of methods through which you can more securely supply these credentials.</span></span>  
  
-   <span data-ttu-id="4dc3f-137">有关如何更安全地提供 BizTalk 解决方案中的 SAP 系统凭据的信息，请参阅[SAP 适配器与 BizTalk Server 安全性](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-137">For information about how to more securely provide SAP system credentials in BizTalk solutions, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="4dc3f-138">有关如何更安全地提供编程解决方案中的 SAP 系统凭据的信息，请参阅[使用 SAP 适配器的安全编程](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-138">For information about how to more securely provide SAP system credentials in programming solutions, see [Secure programming with the SAP adapter](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md).</span></span>  
  
## <a name="security-concerns-for-inbound-scenarios"></a><span data-ttu-id="4dc3f-139">入站方案的安全问题</span><span class="sxs-lookup"><span data-stu-id="4dc3f-139">Security Concerns for Inbound Scenarios</span></span>  
 <span data-ttu-id="4dc3f-140">有权访问 SAP 程序 ID 的任何侦听器可能会接收所有 SAP 项目 （Rfc、 Idoc 和 Trfc） 发送到该程序 id。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-140">Any listener that has access to a SAP program ID can potentially receive all SAP artifacts (RFCs, IDOCs, and tRFCs) sent to that program ID.</span></span> <span data-ttu-id="4dc3f-141">如果多个侦听器已注册到的程序 ID，SAP 将随机分配到的侦听器之一到达该程序 ID 的项目。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-141">If more than one listener is registered to the program ID, SAP will randomly assign artifacts that arrive at that program ID to one of the listeners.</span></span> <span data-ttu-id="4dc3f-142">因此，应，保证你想要使用特定的程序 ID 接收消息的侦听器有权访问该程序 id。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-142">You should, therefore, guarantee that only listeners that you want to receive messages by using a specific program ID have access to that program ID.</span></span> <span data-ttu-id="4dc3f-143">此外，因为 SAP 随机将项目发送到侦听器附加到程序 ID，它是最佳做法将程序 Id 专用于一个侦听器。</span><span class="sxs-lookup"><span data-stu-id="4dc3f-143">Furthermore, because SAP randomly sends artifacts to listeners attached to a program ID, it is a best practice to dedicate program IDs to a single listener.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc3f-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="4dc3f-144">See Also</span></span>  
[<span data-ttu-id="4dc3f-145">最佳做法来保护 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="4dc3f-145">Best practices to secure the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[<span data-ttu-id="4dc3f-146">保护 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="4dc3f-146">Secure your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)