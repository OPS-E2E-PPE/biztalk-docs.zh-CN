---
title: "适用于本机适配器 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45aaf357d943853cc9504762437f554f1d28efb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sso-for-native-adapters"></a><span data-ttu-id="5587d-102">本地适配器的 SSO</span><span class="sxs-lookup"><span data-stu-id="5587d-102">SSO for Native Adapters</span></span>
<span data-ttu-id="5587d-103">使用企业单一登录 (SSO)，您可以在与不同计算机系统或网站进行互操作时只登录一次。</span><span class="sxs-lookup"><span data-stu-id="5587d-103">Enterprise Single Sign-On (SSO) enables you to sign on only once when interoperating with different computer systems or Web sites.</span></span> <span data-ttu-id="5587d-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的此功能使 BizTalk 适配器能够向网络中的多个应用程序（这些应用程序使用基于 Microsoft Windows 凭据的通用验证机制）提供适当的用户 ID 和凭据。</span><span class="sxs-lookup"><span data-stu-id="5587d-104">This feature of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables BizTalk adapters to provide the appropriate user ID and credentials to multiple applications within your network that use a common authentication mechanism based on your Microsoft Windows credentials.</span></span> <span data-ttu-id="5587d-105">Windows 验证凭据之后，您不需要提供其他凭据即可连接到应用程序。</span><span class="sxs-lookup"><span data-stu-id="5587d-105">After Windows authenticates your credentials, you do not need to provide additional credentials to connect to the applications.</span></span>  
  
 <span data-ttu-id="5587d-106">SSO 对 HTTP 和 SOAP 适配器可用，尽管默认情况下它被禁用。</span><span class="sxs-lookup"><span data-stu-id="5587d-106">SSO is available for the HTTP and SOAP adapters, although it is disabled by default.</span></span> <span data-ttu-id="5587d-107">对于 HTTP 适配器，可以配置发送端口和接收位置以使用 SSO；对于 SOAP 适配器，可以仅配置接收位置以使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="5587d-107">For the HTTP adapter, you can configure the send port and receive location to use SSO; for the SOAP adapter, you can configure only the receive location to use SSO.</span></span> <span data-ttu-id="5587d-108">对于这两个适配器，请使用 BizTalk Server 管理控制台来配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="5587d-108">For both adapters, you use the BizTalk Server Administration console to configure SSO.</span></span>  
  
 <span data-ttu-id="5587d-109">SSO 中的验证主要依赖于 Windows 身份验证和在 Active Directory 中创建的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="5587d-109">Authentication in SSO relies primarily on Windows authentication and the Windows groups created in Active Directory.</span></span> <span data-ttu-id="5587d-110">用户或管理员使用 SSO 完成的所有操作都要求 Windows 首先验证用户或管理员的身份。</span><span class="sxs-lookup"><span data-stu-id="5587d-110">All operations completed by a user or administrator with SSO require that Windows authenticate the user or administrator first.</span></span>  
  
 <span data-ttu-id="5587d-111">有关 SSO 如何与 HTTP 和 SOAP 适配器协同工作的详细信息，请参阅“另请参见”部分中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="5587d-111">For more information about how SSO works with the HTTP and SOAP adapters, see the appropriate topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5587d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5587d-112">See Also</span></span>  
 <span data-ttu-id="5587d-113">[使用 SSO](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="5587d-113">[Using SSO](../core/using-sso.md) </span></span>  
 <span data-ttu-id="5587d-114">[HTTP 适配器](../core/http-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5587d-114">[HTTP Adapter](../core/http-adapter.md) </span></span>  
 [<span data-ttu-id="5587d-115">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="5587d-115">SOAP Adapter</span></span>](../core/soap-adapter.md)