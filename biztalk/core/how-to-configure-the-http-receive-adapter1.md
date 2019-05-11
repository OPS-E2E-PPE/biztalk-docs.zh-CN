---
title: 如何配置 HTTP 接收 Adapter1 |Microsoft Docs
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
ms.assetid: e7dbfed3-9dd8-49c9-90b6-a655d7c5446f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd00bdb0b37de46e04e4568019a4f35318e264ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340885"
---
# <a name="how-to-configure-the-http-receive-adapter"></a><span data-ttu-id="269c0-102">如何配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="269c0-102">How to Configure the HTTP Receive Adapter</span></span>
<span data-ttu-id="269c0-103">您可以使用 HTTP 接收适配器将消息提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="269c0-103">You can use the HTTP receive adapter to submit messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="269c0-104">HTTP 接收适配器是在 IIS 进程中托管的 Internet 信息服务 (IIS) ISAPI 扩展。</span><span class="sxs-lookup"><span data-stu-id="269c0-104">The HTTP receive adapter is an Internet Information Services (IIS) ISAPI extension that is hosted in the IIS process.</span></span>  
  
### <a name="to-configure-the-http-receive-adapter"></a><span data-ttu-id="269c0-105">若要配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="269c0-105">To configure the HTTP receive adapter</span></span>  
  
1.  <span data-ttu-id="269c0-106">将 HTTP 接收适配器 (BTSHTTPReceive.dll) 从**\<BizTalk\>\HttpReceive\>** 文件夹包含你的单一登录 (SSO) 项目，例如：</span><span class="sxs-lookup"><span data-stu-id="269c0-106">Copy the HTTP receive adapter (BTSHTTPReceive.dll) from **\<BizTalk\>\HttpReceive\>** to the folder that contains your Single Sign-On (SSO) project, for example:</span></span>  
  
     <span data-ttu-id="269c0-107">**<Adapter_install>\biztalk\SSO\mySSODemo**</span><span class="sxs-lookup"><span data-stu-id="269c0-107">**<Adapter_install>\biztalk\SSO\mySSODemo**</span></span>  
  
    1.  <span data-ttu-id="269c0-108">添加新的 Web 服务扩展添加到 mySSODemo。</span><span class="sxs-lookup"><span data-stu-id="269c0-108">Add a new Web service extension mySSODemo.</span></span>  
  
    2.  <span data-ttu-id="269c0-109">找到并复制 **< BizTalk_install > \HttpReceive**到包含 SSO 项目，例如文件夹：</span><span class="sxs-lookup"><span data-stu-id="269c0-109">Locate and copy **<BizTalk_install>\HttpReceive** to the folder that contains your SSO project, for example:</span></span>  
  
         <span data-ttu-id="269c0-110">**<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**</span><span class="sxs-lookup"><span data-stu-id="269c0-110">**<Adapter_install>\biztalk\SSO\mySSODemo\BTSHTTPReceive.dll.**</span></span>  
  
    3.  <span data-ttu-id="269c0-111">将 mySSODemo Web 服务扩展到的状态设置**允许**。</span><span class="sxs-lookup"><span data-stu-id="269c0-111">Set the status of mySSODemo Web service extension to **Allowed**.</span></span>  
  
2.  <span data-ttu-id="269c0-112">重新启动 IIS 以应用所有更改。</span><span class="sxs-lookup"><span data-stu-id="269c0-112">Restart IIS to apply all changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269c0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="269c0-113">See Also</span></span>  
 [<span data-ttu-id="269c0-114">保护适配器</span><span class="sxs-lookup"><span data-stu-id="269c0-114">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)