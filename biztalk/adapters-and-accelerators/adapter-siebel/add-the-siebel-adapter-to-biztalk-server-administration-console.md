---
title: 将 Siebel 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b64d0bdc-ac83-46c9-b27d-625088a013d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f8c30567849a0342432cb53e0c2de7959c175c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967422"
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="c85bf-102">将 Siebel 适配器添加到 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c85bf-102">Add the Siebel Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="c85bf-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 Wcf-siebel 端口使用。</span><span class="sxs-lookup"><span data-stu-id="c85bf-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-Siebel port.</span></span> <span data-ttu-id="c85bf-104">如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。</span><span class="sxs-lookup"><span data-stu-id="c85bf-104">If you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="c85bf-105">但是，如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF Siebel 端口，必须首先添加 Wcf-siebel 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c85bf-105">However, if you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Siebel port, you must first add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="c85bf-106">本主题说明了如何添加 Wcf-siebel 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c85bf-106">This topic provides instructions on how to add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c85bf-107">如果你想要配置 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c85bf-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="add-the-siebel-adapter"></a><span data-ttu-id="c85bf-108">将 Siebel 适配器添加</span><span class="sxs-lookup"><span data-stu-id="c85bf-108">Add the Siebel adapter</span></span>  
  
1. <span data-ttu-id="c85bf-109">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c85bf-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="c85bf-110">在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="c85bf-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="c85bf-111">右键单击**适配器**，依次指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="c85bf-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="c85bf-112">![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="c85bf-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="c85bf-113">在中**适配器属性**对话框框中，指定名称的适配器，从**适配器**列表中，选择**Wcf-siebel**。</span><span class="sxs-lookup"><span data-stu-id="c85bf-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-Siebel**.</span></span>  
  
    <span data-ttu-id="c85bf-114">![添加 WCF&#45;Siebel 适配器添加到 BizTalk 控制台](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")</span><span class="sxs-lookup"><span data-stu-id="c85bf-114">![Add WCF&#45;Siebel adapter to BizTalk console](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")</span></span>  
  
5. <span data-ttu-id="c85bf-115">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c85bf-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85bf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c85bf-116">See Also</span></span>  
[<span data-ttu-id="c85bf-117">若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="c85bf-117">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)