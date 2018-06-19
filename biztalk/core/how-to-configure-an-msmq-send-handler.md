---
title: 如何配置 MSMQ 发送处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feacaec9d2794cf8806fa5156fe64b7290699faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248261"
---
# <a name="how-to-configure-an-msmq-send-handler"></a><span data-ttu-id="31d1f-102">如何配置 MSMQ 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="31d1f-102">How to Configure an MSMQ Send Handler</span></span>
<span data-ttu-id="31d1f-103">使用下面的步骤可以更改 MSMQ 发送处理程序的全局变量。</span><span class="sxs-lookup"><span data-stu-id="31d1f-103">Use the following procedure to change the global variables for an MSMQ send handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31d1f-104">每个主机只能有一个关联的发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="31d1f-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a><span data-ttu-id="31d1f-105">通过使用 BizTalk Server 管理控制台更改 MSMQ 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="31d1f-105">To change global variables for an MSMQ send handler by using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="31d1f-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="31d1f-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="31d1f-107">在展开的适配器列表中，单击**MSMQ**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="31d1f-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="31d1f-108">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择的主机发送处理程序将与之相关联，并依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="31d1f-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="31d1f-109">在**MSMQ 传输属性**对话框框中，输入一个值**批大小**。</span><span class="sxs-lookup"><span data-stu-id="31d1f-109">In the **MSMQ Transport Properties** dialog box, enter a value for **Batch Size**.</span></span>  
  
     <span data-ttu-id="31d1f-110">MSMQ 发送处理程序会将消息发送到使用指定的目标队列**批大小**参数。</span><span class="sxs-lookup"><span data-stu-id="31d1f-110">The MSMQ send handler will send messages to destination queues using the specified **Batch Size** parameter.</span></span> <span data-ttu-id="31d1f-111">默认值**批大小**值为 5。</span><span class="sxs-lookup"><span data-stu-id="31d1f-111">The default **Batch Size** value is 5.</span></span>  
  
5.  <span data-ttu-id="31d1f-112">单击**确定**单击**确定**以关闭**适配器处理程序属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="31d1f-112">Click **OK** and click **OK** again to close the **Adapter Handler Properties** dialog box.</span></span>