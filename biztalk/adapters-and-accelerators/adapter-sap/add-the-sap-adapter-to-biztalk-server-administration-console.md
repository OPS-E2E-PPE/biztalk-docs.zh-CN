---
title: 将 SAP 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019edf01b4635777a91ac00efa0e2facebc7d1c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374271"
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="4d9d5-102">将 SAP 适配器添加到 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4d9d5-102">Add the SAP Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="4d9d5-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 WCF SAP 端口使用。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SAP port.</span></span> <span data-ttu-id="4d9d5-104">如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-104">If you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="4d9d5-105">但是，如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF SAP 端口，必须首先添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-105">However, if you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-SAP port, you must first add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="4d9d5-106">本主题说明了如何添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-106">This topic provides instructions on how to add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4d9d5-107">如果你想要配置 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="add-the-sap-adapter"></a><span data-ttu-id="4d9d5-108">添加 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="4d9d5-108">Add the SAP Adapter</span></span>  
  
1. <span data-ttu-id="4d9d5-109">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="4d9d5-110">在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="4d9d5-111">右键单击**适配器**，依次指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="4d9d5-112">![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="4d9d5-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="4d9d5-113">在中**适配器属性**对话框框中，指定名称的适配器，从**适配器**列表中，选择**WCF SAP**。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-SAP**.</span></span>  
  
    <span data-ttu-id="4d9d5-114">![将 SAP 适配器添加到 BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="4d9d5-114">![Add SAP Adapter to BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  
  
5. <span data-ttu-id="4d9d5-115">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4d9d5-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9d5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d9d5-116">See Also</span></span>  
[<span data-ttu-id="4d9d5-117">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="4d9d5-117">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)