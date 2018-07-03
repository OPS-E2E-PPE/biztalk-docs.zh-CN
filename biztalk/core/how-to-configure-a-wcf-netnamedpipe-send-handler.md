---
title: 如何配置 Wcf-netnamedpipe 发送处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, global adapters
- configuring [WCF-NetNamedPipe adapters], global adapters
- send handlers, WCF-NetNamedPipe adapters
- configuring [WCF-NetNamedPipe adapters], send handlers
ms.assetid: 1f281649-d09f-44eb-8af5-1f83233fab60
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9ef8086ae0cda04da3ecdc7eacbfcb6d01f14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970222"
---
# <a name="how-to-configure-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="8ed4d-102">如何配置 WCF-NetNamedPipe 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="8ed4d-102">How to Configure a WCF-NetNamedPipe Send Handler</span></span>
<span data-ttu-id="8ed4d-103">使用以下过程可配置 WCF-NetNamedPipe 发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-103">Use the following procedure to configure a WCF-NetNamedPipe send handler.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-netnamedpipe-send-handler"></a><span data-ttu-id="8ed4d-104">更改 WCF-NetNamedPipe 发送处理程序的全局变量</span><span class="sxs-lookup"><span data-stu-id="8ed4d-104">To change global variables for a WCF-NetNamedPipe send handler</span></span>  

1. <span data-ttu-id="8ed4d-105">在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-105">In the BizTalk Server Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="8ed4d-106">在展开的适配器列表中，单击**Wcf-netnamedpipe**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-106">In the expanded adapter list, click **WCF-NetNamedPipe**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="8ed4d-107">在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择发送处理程序将关联的主机。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated.</span></span>  

4. <span data-ttu-id="8ed4d-108">在中**常规**选项卡上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-108">In the **General** tab, click **Properties**.</span></span> <span data-ttu-id="8ed4d-109">上**发送处理程序**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8ed4d-109">On the **Send handler** tab, do the following:</span></span>  


   |        <span data-ttu-id="8ed4d-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8ed4d-110">Use this</span></span>         |                                                                                                                                                                                                                                                                             <span data-ttu-id="8ed4d-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8ed4d-111">To do this</span></span>                                                                                                                                                                                                                                                                             |
   |-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="8ed4d-112">**最大连接数**</span><span class="sxs-lookup"><span data-stu-id="8ed4d-112">**Maximum connections**</span></span> | <span data-ttu-id="8ed4d-113">为在连接池中缓存的各终结点指定最大出站连接数。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-113">Specify the maximum number of outbound connections for each endpoint that is cached in the connection pool.</span></span> <span data-ttu-id="8ed4d-114">这将限制为每个唯一的远程终结点缓存的连接数。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-114">This limits the number of connections that are cached for each unique remote endpoint.</span></span> <span data-ttu-id="8ed4d-115">对于每个唯一的远程终结点，你应该将此值设置为一个大于最大期望缓存连接数的值。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-115">You should set this value to be greater than the maximum number of connections that you expect to be cached for any unique remote endpoint.</span></span> <span data-ttu-id="8ed4d-116">如果活动的出站连接的数目超过此最大值，则服务可能不响应运行在此发送处理程序下的 WCF-NetNamedPipe 发送端口。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-116">If the number of active outbound connections exceeds this maximum value, then the service may appear unresponsive to the WCF-NetNamedPipe send ports running under this send hander.</span></span><br /><br /> <span data-ttu-id="8ed4d-117">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-117">The default is 10.</span></span> |


5. <span data-ttu-id="8ed4d-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="8ed4d-118">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8ed4d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ed4d-119">See Also</span></span>  
 <span data-ttu-id="8ed4d-120">[使用 WCF 服务](../core/consuming-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="8ed4d-120">[Consuming WCF Services](../core/consuming-wcf-services.md) </span></span>  
 [<span data-ttu-id="8ed4d-121">配置 WCF-NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="8ed4d-121">Configuring the WCF-NetNamedPipe Adapter</span></span>](../core/configuring-the-wcf-netnamedpipe-adapter.md)