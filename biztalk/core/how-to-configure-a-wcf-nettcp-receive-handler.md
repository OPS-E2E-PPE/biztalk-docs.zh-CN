---
title: 如何配置 Wcf-nettcp 接收处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, global variables
- receive handlers, WCF-NetTcp adapters
- configuring [WCF-NetTcp adapters], global variables
- configuring [WCF-NetTcp adapters], receive handlers
ms.assetid: a4a283d1-21de-4d6b-9cb5-f2f9f823903b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48133eaa50fed0062b17d9e3b25fe180d7495f89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342196"
---
# <a name="how-to-configure-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="99533-102">如何配置 WCF-NetTcp 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="99533-102">How to Configure a WCF-NetTcp Receive Handler</span></span>
<span data-ttu-id="99533-103">使用以下过程配置 Wcf-nettcp 接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="99533-103">Use the following procedure to configure a WCF-NetTcp receive handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-nettcp-receive-handler"></a><span data-ttu-id="99533-104">若要更改全局变量的 Wcf-nettcp 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="99533-104">To change global variables for a WCF-NetTcp receive handler</span></span>  

1. <span data-ttu-id="99533-105">在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="99533-105">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="99533-106">在展开的适配器列表中，单击**WCF NetTcp**，在右窗格中，右键单击你想要配置，接收处理程序，再单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="99533-106">In the expanded adapter list, click **WCF-NetTcp**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="99533-107">在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将关联的主机。</span><span class="sxs-lookup"><span data-stu-id="99533-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="99533-108">在中**常规**选项卡上，单击**属性**，然后在**接收处理程序**选项卡上，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="99533-108">In the **General** tab, click **Properties**, On the **Receive handler** tab, do the following.</span></span>  


   |        <span data-ttu-id="99533-109">使用此选项</span><span class="sxs-lookup"><span data-stu-id="99533-109">Use this</span></span>         |                                                                                                                         <span data-ttu-id="99533-110">执行的操作</span><span class="sxs-lookup"><span data-stu-id="99533-110">To do this</span></span>                                                                                                                         |
   |-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="99533-111">**最大连接数**</span><span class="sxs-lookup"><span data-stu-id="99533-111">**Maximum connections**</span></span> | <span data-ttu-id="99533-112">指定的最大侦听器可以拥有等待接受的应用程序的连接数。</span><span class="sxs-lookup"><span data-stu-id="99533-112">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="99533-113">当超过此配额值时，会删除新的传入连接而不是等待接受。</span><span class="sxs-lookup"><span data-stu-id="99533-113">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span><br /><br /> <span data-ttu-id="99533-114">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="99533-114">The default is 10.</span></span> |


5. <span data-ttu-id="99533-115">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="99533-115">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="99533-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="99533-116">See Also</span></span>  
 <span data-ttu-id="99533-117">[配置 Wcf-nettcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="99533-117">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="99533-118">发布 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="99533-118">Publishing WCF Services</span></span>](../core/publishing-wcf-services.md)