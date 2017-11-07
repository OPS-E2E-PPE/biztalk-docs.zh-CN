---
title: "如何配置 HTTP 接收 Adapter2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6e40036308aa872a2d6ba23da8209ee9f80cfc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="d55c8-102">如何配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="d55c8-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="d55c8-103">您可以使用 HTTP 接收适配器将消息提交到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d55c8-103">You can use the HTTP receive adapter to submit messages to BizTalk Server.</span></span> <span data-ttu-id="d55c8-104">HTTP 接收适配器是承载于 IIS 进程的 Internet 信息服务 (IIS) ISAPI 扩展。</span><span class="sxs-lookup"><span data-stu-id="d55c8-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="d55c8-105">若要配置 HTTP 接收适配器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d55c8-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="d55c8-106">复制 HTTP 从接收适配器 (BTSHTTPReceive.dll)  **\<BizTalk2010 > \HttpReceive >**到包含你的单一登录 (SSO) 项目的文件夹 (例如， **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。</span><span class="sxs-lookup"><span data-stu-id="d55c8-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk2010>\HttpReceive>** to the folder containing your Single Sign-On (SSO) project (for example, **<Adapter_install>\biztalk2010\SSO\mySSODemo**).</span></span>  
  
    1.  <span data-ttu-id="d55c8-107">将新的 Web 服务扩展添加到 mySSODemo。</span><span class="sxs-lookup"><span data-stu-id="d55c8-107">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="d55c8-108">例如，浏览到 <BizTalk_install>\HttpReceive，并将其复制到包含 SSO 项目的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d55c8-108">Browse to and copy <BizTalk_install>\HttpReceive to the folder containing your SSO project, for example,</span></span>  
  
         <span data-ttu-id="d55c8-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll。</span><span class="sxs-lookup"><span data-stu-id="d55c8-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span></span>  
  
    3.  <span data-ttu-id="d55c8-110">设置到 mySSODemo Web 服务扩展的状态**允许**。</span><span class="sxs-lookup"><span data-stu-id="d55c8-110">Set status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="d55c8-111">重新启动 IIS 以确保所有更改都生效。</span><span class="sxs-lookup"><span data-stu-id="d55c8-111">Restart IIS to ensure that all changes are in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55c8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d55c8-112">See Also</span></span>  
 [<span data-ttu-id="d55c8-113">适配器中的安全</span><span class="sxs-lookup"><span data-stu-id="d55c8-113">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)