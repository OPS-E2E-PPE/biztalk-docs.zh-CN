---
title: "如何为博士 Edwards OneWorld 创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 858425ef-bdb7-4d2d-90ca-b3655e389749
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc77fd72171983ab2fbc7de42ddf36d770d045c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="b651c-102">如何创建 JD Edwards OneWorld 的发送端口</span><span class="sxs-lookup"><span data-stu-id="b651c-102">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="b651c-103">使用以下过程创建发送端口。</span><span class="sxs-lookup"><span data-stu-id="b651c-103">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="b651c-104">创建发送端口的步骤</span><span class="sxs-lookup"><span data-stu-id="b651c-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="b651c-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后导航到所需的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b651c-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="b651c-106">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b651c-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b651c-107">你还可以使用**静态单向端口**。</span><span class="sxs-lookup"><span data-stu-id="b651c-107">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="b651c-108">在**发送端口属性**对话框中，在**名称**字段中，键入发送端口名称 (例如，键入**SendToJDE**。)</span><span class="sxs-lookup"><span data-stu-id="b651c-108">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="b651c-109">在**类型**下拉列表中，选择**JDEOneWorld**。</span><span class="sxs-lookup"><span data-stu-id="b651c-109">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="b651c-110">在**URI**下拉列表中，选择发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="b651c-110">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="b651c-111">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b651c-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b651c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b651c-112">See Also</span></span>  
 [<span data-ttu-id="b651c-113">创建博士 Edwards OneWorld 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="b651c-113">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)