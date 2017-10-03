---
title: "如何配置 WCF NetNamedPipe 接收处理程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [WCF-NetNamedPipe adapters], global variables
- receive handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], receive handlers
- WCF-NetNamedPipe adapters, global variables
ms.assetid: f7ab2228-1049-40f0-87f7-6330a8f40cfe
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9339cca7f8065d3412686cfcc84d84028ef39faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-netnamedpipe-receive-handler"></a><span data-ttu-id="7440e-102">如何配置 WCF-NetNamedPipe 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="7440e-102">How to Configure a WCF-NetNamedPipe Receive Handler</span></span>
<span data-ttu-id="7440e-103">可使用以下过程配置 WCF-NetNamedPipe 接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="7440e-103">Use the following procedure to configure a WCF-NetNamedPipe receive handler.</span></span>  
  
### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-receive-handler"></a><span data-ttu-id="7440e-104">更改 WCF-NetNamedPipe 接收处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="7440e-104">To change global variables for a WCF-NetNamedPipe receive handler</span></span>  
  
1.  <span data-ttu-id="7440e-105">在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="7440e-105">In the BizTalk Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="7440e-106">在展开的适配器列表中，单击**WCF NetNamedPipe**，而是在右窗格中，右键单击你想要配置，接收处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7440e-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="7440e-107">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之关联的主机。</span><span class="sxs-lookup"><span data-stu-id="7440e-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="7440e-108">在**常规**选项卡上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7440e-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="7440e-109">上**接收处理程序**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7440e-109">On the **Receive handler** tab, do the following:</span></span>  
  
    |<span data-ttu-id="7440e-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="7440e-110">Use this</span></span>|<span data-ttu-id="7440e-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="7440e-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7440e-112">**最大连接数**</span><span class="sxs-lookup"><span data-stu-id="7440e-112">**Maximum connections**</span></span>|<span data-ttu-id="7440e-113">指定监听程序可以拥有的等待应用程序接受的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="7440e-113">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="7440e-114">在超过此配额值时，将删除新的传入连接，而不是等待接受这些连接。</span><span class="sxs-lookup"><span data-stu-id="7440e-114">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="7440e-115">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="7440e-115">The default is 10.</span></span>|  
  
5.  <span data-ttu-id="7440e-116">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7440e-116">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7440e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7440e-117">See Also</span></span>  
 <span data-ttu-id="7440e-118">[发布的 WCF 服务](../core/publishing-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="7440e-118">[Publishing WCF Services](../core/publishing-wcf-services.md) </span></span>  
 [<span data-ttu-id="7440e-119">配置 WCF NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="7440e-119">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)