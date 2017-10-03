---
title: "如何配置 HTTP 接收 Adapter1 |Microsoft 文档"
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
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed6907a96c3c961a4df7d076ba9307f44627bfa2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="e001d-102">如何配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="e001d-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="e001d-103">您可以使用 HTTP 接收适配器将消息提交到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e001d-103">You can use the HTTP receive adapter to submit messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e001d-104">HTTP 接收适配器是承载于 IIS 进程的 Internet 信息服务 (IIS) ISAPI 扩展。</span><span class="sxs-lookup"><span data-stu-id="e001d-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="e001d-105">若要配置 HTTP 接收适配器，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e001d-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="e001d-106">复制 HTTP 从接收适配器 (BTSHTTPReceive.dll)  **\<BizTalk > \HttpReceive >**包含你的单一登录 (SSO) 项目，例如的文件夹：</span><span class="sxs-lookup"><span data-stu-id="e001d-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk>\HttpReceive>** to the folder that contains your Single Sign-On (SSO) project, for example:</span></span>  
  
     <span data-ttu-id="e001d-107">**< Adapter_install > \biztalk\SSO\mySSODemo**</span><span class="sxs-lookup"><span data-stu-id="e001d-107">**<Adapter_install>\biztalk\SSO\mySSODemo**</span></span>  
  
    1.  <span data-ttu-id="e001d-108">将新的 Web 服务扩展添加到 mySSODemo。</span><span class="sxs-lookup"><span data-stu-id="e001d-108">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="e001d-109">查找并复制**< BizTalk_install > \HttpReceive**例如包含 SSO 项目的文件夹：</span><span class="sxs-lookup"><span data-stu-id="e001d-109">Locate and copy **<BizTalk_install>\HttpReceive** to the folder that contains your SSO project, for example:</span></span>  
  
         <span data-ttu-id="e001d-110">**< Adapter_install > \biztalk\SSO\mySSODemo\BTSHTTPReceive.dll。**</span><span class="sxs-lookup"><span data-stu-id="e001d-110">**<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**</span></span>  
  
    3.  <span data-ttu-id="e001d-111">设置到 mySSODemo Web 服务扩展的状态**允许**。</span><span class="sxs-lookup"><span data-stu-id="e001d-111">Set the status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="e001d-112">重新启动 IIS 将应用所有更改。</span><span class="sxs-lookup"><span data-stu-id="e001d-112">Restart IIS to apply all changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e001d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e001d-113">See Also</span></span>  
 [<span data-ttu-id="e001d-114">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="e001d-114">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)