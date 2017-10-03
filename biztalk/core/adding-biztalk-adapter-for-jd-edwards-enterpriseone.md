---
title: "为博士 Edwards EnterpriseOne 添加 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, JD Edwards EnterpriseOne adapters
- JD Edwards EnterpriseOne adapters, installing
- adapters [JD Edwards EnterpriseOne adapters], installing
ms.assetid: baecebcd-c324-40aa-bacf-876f45b6c37f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ab141d8f3227c12abd9a790bc82fa8f9ada3ae8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="74f6b-102">添加 JD Edwards EnterpriseOne 的  BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="74f6b-102">Adding BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="74f6b-103">用于 J.D.Edwards EnterpriseOne 的 Microsoft BizTalk 适配器包含接收处理程序和发送处理程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="74f6b-103">Microsoft BizTalk Adapter for J.D.Edwards EnterpriseOne contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="74f6b-104">这两个文件夹包含 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="74f6b-104">The folders contain BizTalkServerApplication.</span></span> <span data-ttu-id="74f6b-105">用于 J.D.Edwards EnterpriseOne 的 BizTalk 适配器是可创建的；它在 BizTalk Server 进程内运行，而不是在独立的主机进程中运行。</span><span class="sxs-lookup"><span data-stu-id="74f6b-105">BizTalk Adapter for J.D.Edwards EnterpriseOne is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
### <a name="to-add-the-adapter-to-biztalk-server"></a><span data-ttu-id="74f6b-106">将适配器添加到 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="74f6b-106">To add the adapter to BizTalk Server</span></span>  
  
1.  <span data-ttu-id="74f6b-107">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="74f6b-107">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="74f6b-108">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**平台设置**。</span><span class="sxs-lookup"><span data-stu-id="74f6b-108">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="74f6b-109">右键单击**适配器**，指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="74f6b-109">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="74f6b-110">键入适配器; 的名称例如， `JDEEnterpriseOne`。</span><span class="sxs-lookup"><span data-stu-id="74f6b-110">Type a name for the adapter; for example, `JDEEnterpriseOne`.</span></span>  
  
5.  <span data-ttu-id="74f6b-111">选择**JDEEnterpriseOne**从**适配器**列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="74f6b-111">Select **JDEEnterpriseOne** from the **Adapter** list, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f6b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f6b-112">See Also</span></span>  
 [<span data-ttu-id="74f6b-113">开发应用程序</span><span class="sxs-lookup"><span data-stu-id="74f6b-113">Developing Applications</span></span>](../core/developing-applications2.md)