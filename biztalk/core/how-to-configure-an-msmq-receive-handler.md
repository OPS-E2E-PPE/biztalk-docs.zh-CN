---
title: 如何配置 MSMQ 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, MSMQ adapters
- configuring [MSMQ adapters], receive handlers
- MSMQ adapters, receive handlers
ms.assetid: d6d82098-3a73-44e2-80d5-143f77e919cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61741921363caa96acc2cb1a1e787ad1fbd41120
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386424"
---
# <a name="how-to-configure-an-msmq-receive-handler"></a><span data-ttu-id="6bec9-102">如何配置 MSMQ 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="6bec9-102">How to Configure an MSMQ Receive Handler</span></span>
<span data-ttu-id="6bec9-103">使用以下过程来更改与 MSMQ 接收处理程序的主机程序关联。</span><span class="sxs-lookup"><span data-stu-id="6bec9-103">Use the following procedure to change the host with which the MSMQ receive handler is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bec9-104">只有一个接收处理程序，可以与关联的每个主机。</span><span class="sxs-lookup"><span data-stu-id="6bec9-104">Each host can associate with only one receive handler.</span></span>  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a><span data-ttu-id="6bec9-105">若要更改与 MSMQ 接收处理程序的主机是关联</span><span class="sxs-lookup"><span data-stu-id="6bec9-105">To change the host with which the MSMQ receive handler is associated</span></span>  
  
1.  <span data-ttu-id="6bec9-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="6bec9-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="6bec9-107">在展开的适配器列表中，单击**MSMQ**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6bec9-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6bec9-108">在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。</span><span class="sxs-lookup"><span data-stu-id="6bec9-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="6bec9-109">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6bec9-109">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bec9-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bec9-110">See Also</span></span>  
 [<span data-ttu-id="6bec9-111">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="6bec9-111">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)