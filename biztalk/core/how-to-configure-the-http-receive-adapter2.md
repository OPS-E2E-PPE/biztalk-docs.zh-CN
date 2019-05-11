---
title: 如何配置 HTTP 接收 Adapter2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP receive adapter, configuring
- configuring HTTP receive adapter
ms.assetid: dd26fd57-90d8-4ffe-b56f-8de55ecc6f68
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73b04356f7c09d8aa2a24d816f02dc66e5d414d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340843"
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="75e0d-102">如何配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="75e0d-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="75e0d-103">您可以使用 HTTP 接收适配器将消息提交给 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="75e0d-103">You can use the HTTP receive adapter to submit messages to BizTalk Server.</span></span> <span data-ttu-id="75e0d-104">HTTP 接收适配器是在 IIS 进程中托管的 Internet 信息服务 (IIS) ISAPI 扩展。</span><span class="sxs-lookup"><span data-stu-id="75e0d-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="75e0d-105">若要配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="75e0d-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="75e0d-106">将 HTTP 接收适配器 (BTSHTTPReceive.dll) 从 **\<BizTalk2010 > \HttpReceive >** 包含单一登录 (SSO) 项目的文件夹 (例如， **< Adapter_install > \biztalk2010\SSO\mySSODemo**)。</span><span class="sxs-lookup"><span data-stu-id="75e0d-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk2010>\HttpReceive>** to the folder containing your Single Sign-On (SSO) project (for example, **<Adapter_install>\biztalk2010\SSO\mySSODemo**).</span></span>  
  
    1.  <span data-ttu-id="75e0d-107">添加新的 Web 服务扩展添加到 mySSODemo。</span><span class="sxs-lookup"><span data-stu-id="75e0d-107">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="75e0d-108">浏览到并复制 < BizTalk_install > \HttpReceive 到文件夹包含 SSO 项目，例如，</span><span class="sxs-lookup"><span data-stu-id="75e0d-108">Browse to and copy <BizTalk_install>\HttpReceive to the folder containing your SSO project, for example,</span></span>  
  
         <span data-ttu-id="75e0d-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span><span class="sxs-lookup"><span data-stu-id="75e0d-109"><Adapter_install>\biztalk2010\SSO\mySSODemo\BTSHTTPReceive.dll.</span></span>  
  
    3.  <span data-ttu-id="75e0d-110">将 mySSODemo Web 服务扩展到的状态设置**允许**。</span><span class="sxs-lookup"><span data-stu-id="75e0d-110">Set status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="75e0d-111">重新启动 IIS 以确保所有更改都都生效。</span><span class="sxs-lookup"><span data-stu-id="75e0d-111">Restart IIS to ensure that all changes are in effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e0d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="75e0d-112">See Also</span></span>  
 [<span data-ttu-id="75e0d-113">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="75e0d-113">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)