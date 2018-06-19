---
title: 如何配置一个 POP3 接收处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, POP3 adapters
- POP3 adapters, receive handlers
- configuring [POP3 adapters], receive handlers
ms.assetid: 2191c201-545e-4d5a-a1ca-3c38c7b8258d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8868ce589fa7556da185dcaf4c71b5bfd5cae159
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247781"
---
# <a name="how-to-configure-a-pop3-receive-handler"></a><span data-ttu-id="8327e-102">如何配置一个 POP3 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="8327e-102">How to Configure a POP3 Receive Handler</span></span>
<span data-ttu-id="8327e-103">使用下面的步骤更改与 POP3 接收处理程序关联的主机。</span><span class="sxs-lookup"><span data-stu-id="8327e-103">Use the following procedure to change the host associated with the POP3 receive handler.</span></span>  
  
### <a name="to-configure-the-general-properties-for-a-pop3-receive-handler"></a><span data-ttu-id="8327e-104">配置 POP3 接收处理程序的常规属性</span><span class="sxs-lookup"><span data-stu-id="8327e-104">To configure the general properties for a POP3 receive handler</span></span>  
  
1.  <span data-ttu-id="8327e-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="8327e-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="8327e-106">在展开的适配器列表中，单击**POP3**，而是在右窗格中，右键单击你想要配置，接收处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8327e-106">In the expanded adapter list, click **POP3**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="8327e-107">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。</span><span class="sxs-lookup"><span data-stu-id="8327e-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="8327e-108">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8327e-108">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8327e-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8327e-109">See Also</span></span>  
 [<span data-ttu-id="8327e-110">运行在群集主机内的适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="8327e-110">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)