---
title: 本地适配器的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d526f9b3cfc0e6b749469151606f4ae19ce454f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258599"
---
# <a name="sso-for-native-adapters"></a><span data-ttu-id="25b66-102">本地适配器的 SSO</span><span class="sxs-lookup"><span data-stu-id="25b66-102">SSO for Native Adapters</span></span>
<span data-ttu-id="25b66-103">企业单一登录 (SSO)，可只登录一次使用不同的计算机系统或网站进行互操作时。</span><span class="sxs-lookup"><span data-stu-id="25b66-103">Enterprise Single Sign-On (SSO) enables you to sign on only once when interoperating with different computer systems or Web sites.</span></span> <span data-ttu-id="25b66-104">Microsoft 的这一功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使 BizTalk 适配器能够提供适当的用户 ID 和多个应用程序在网络中使用基于 Microsoft Windows 凭据的常见身份验证机制的凭据。</span><span class="sxs-lookup"><span data-stu-id="25b66-104">This feature of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables BizTalk adapters to provide the appropriate user ID and credentials to multiple applications within your network that use a common authentication mechanism based on your Microsoft Windows credentials.</span></span> <span data-ttu-id="25b66-105">Windows 对你的凭据进行身份验证后，您不需要提供其他凭据即可连接到应用程序。</span><span class="sxs-lookup"><span data-stu-id="25b66-105">After Windows authenticates your credentials, you do not need to provide additional credentials to connect to the applications.</span></span>  
  
 <span data-ttu-id="25b66-106">SSO 是可用于 HTTP 和 SOAP 适配器，尽管默认情况下禁用。</span><span class="sxs-lookup"><span data-stu-id="25b66-106">SSO is available for the HTTP and SOAP adapters, although it is disabled by default.</span></span> <span data-ttu-id="25b66-107">HTTP 适配器，您可以配置发送端口和接收位置以使用 SSO;对于 SOAP 适配器，可以配置仅接收位置以使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="25b66-107">For the HTTP adapter, you can configure the send port and receive location to use SSO; for the SOAP adapter, you can configure only the receive location to use SSO.</span></span> <span data-ttu-id="25b66-108">对于这两个适配器，使用 BizTalk Server 管理控制台来配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="25b66-108">For both adapters, you use the BizTalk Server Administration console to configure SSO.</span></span>  
  
 <span data-ttu-id="25b66-109">SSO 中的身份验证主要依赖于 Windows 身份验证和 Active Directory 中创建的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="25b66-109">Authentication in SSO relies primarily on Windows authentication and the Windows groups created in Active Directory.</span></span> <span data-ttu-id="25b66-110">由用户或管理员使用 SSO 完成的所有操作都要求，Windows 先进行身份验证的用户或管理员。</span><span class="sxs-lookup"><span data-stu-id="25b66-110">All operations completed by a user or administrator with SSO require that Windows authenticate the user or administrator first.</span></span>  
  
 <span data-ttu-id="25b66-111">有关使用 HTTP 和 SOAP 适配器的 SSO 工作原理的详细信息，请参阅另请参阅中的相应主题。</span><span class="sxs-lookup"><span data-stu-id="25b66-111">For more information about how SSO works with the HTTP and SOAP adapters, see the appropriate topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b66-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="25b66-112">See Also</span></span>  
 <span data-ttu-id="25b66-113">[使用 SSO](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="25b66-113">[Using SSO](../core/using-sso.md) </span></span>  
 <span data-ttu-id="25b66-114">[HTTP 适配器](../core/http-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="25b66-114">[HTTP Adapter](../core/http-adapter.md) </span></span>  
 [<span data-ttu-id="25b66-115">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="25b66-115">SOAP Adapter</span></span>](../core/soap-adapter.md)