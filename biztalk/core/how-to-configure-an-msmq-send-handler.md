---
title: 如何配置 MSMQ 发送处理程序 |Microsoft Docs
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
ms.openlocfilehash: 3f1ca5c7eb79f38671cc7e257b184125740ed0d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386431"
---
# <a name="how-to-configure-an-msmq-send-handler"></a><span data-ttu-id="28cfa-102">如何配置 MSMQ 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="28cfa-102">How to Configure an MSMQ Send Handler</span></span>
<span data-ttu-id="28cfa-103">使用以下过程来更改全局变量 msmq 发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="28cfa-103">Use the following procedure to change the global variables for an MSMQ send handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28cfa-104">每个主机可以只有一个与其关联的发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="28cfa-104">Each host can have only one send handler associated with it.</span></span>  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a><span data-ttu-id="28cfa-105">若要更改全局变量 msmq 发送处理程序通过使用 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="28cfa-105">To change global variables for an MSMQ send handler by using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="28cfa-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="28cfa-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="28cfa-107">在展开的适配器列表中，单击**MSMQ**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="28cfa-107">In the expanded adapter list, click **MSMQ**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="28cfa-108">在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择将的主机与发送处理程序相关联，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="28cfa-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="28cfa-109">在中**MSMQ 传输属性**对话框框中，输入一个值**批大小**。</span><span class="sxs-lookup"><span data-stu-id="28cfa-109">In the **MSMQ Transport Properties** dialog box, enter a value for **Batch Size**.</span></span>  
  
     <span data-ttu-id="28cfa-110">MSMQ 发送处理程序将消息发送到使用指定的目标队列**批大小**参数。</span><span class="sxs-lookup"><span data-stu-id="28cfa-110">The MSMQ send handler will send messages to destination queues using the specified **Batch Size** parameter.</span></span> <span data-ttu-id="28cfa-111">默认值**批大小**值为 5。</span><span class="sxs-lookup"><span data-stu-id="28cfa-111">The default **Batch Size** value is 5.</span></span>  
  
5.  <span data-ttu-id="28cfa-112">单击**确定**然后单击**确定**以关闭**适配器处理程序属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="28cfa-112">Click **OK** and click **OK** again to close the **Adapter Handler Properties** dialog box.</span></span>