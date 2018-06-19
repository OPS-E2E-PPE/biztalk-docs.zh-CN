---
title: 将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b126aa-2a05-49fa-80e1-f1d5c21ad60f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492a99d8835990ee630dfb0ad0603279873eca4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216525"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="5dcea-102">将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="5dcea-102">Add the Oracle E-Business Suite adapter to BizTalk Server Administration console</span></span>
<span data-ttu-id="5dcea-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以作为 WCF 自定义端口或 WCF OracleEBS 端口在 BizTalk Server 中使用。</span><span class="sxs-lookup"><span data-stu-id="5dcea-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] can be used in BizTalk Server either as a WCF-Custom port or a WCF-OracleEBS port.</span></span> <span data-ttu-id="5dcea-104">如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5dcea-104">If you want to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="5dcea-105">但是，如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF OracleEBS 端口，您必须首先添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5dcea-105">However, if you want to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] through a WCF-OracleEBS port, you must first add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="5dcea-106">本主题将说明了如何将添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5dcea-106">This topic provides instructions on how to add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5dcea-107">如果你想要配置的 WCF 自定义端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，无需执行此过程。</span><span class="sxs-lookup"><span data-stu-id="5dcea-107">If you want to configure a WCF-Custom port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you need not perform this procedure.</span></span>  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="5dcea-108">若要添加 Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="5dcea-108">To add the Oracle E-Business Suite Adapter</span></span>  
  
1.  <span data-ttu-id="5dcea-109">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5dcea-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="5dcea-110">在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="5dcea-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3.  <span data-ttu-id="5dcea-111">右键单击**适配器**，指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="5dcea-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
     <span data-ttu-id="5dcea-112">![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="5dcea-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="5dcea-113">在**适配器属性**对话框框中，指定的名称为适配器并从**适配器**列表中，选择**WCF OracleEBS**。</span><span class="sxs-lookup"><span data-stu-id="5dcea-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-OracleEBS**.</span></span>  
  
     <span data-ttu-id="5dcea-114">![WCF &#45; 添加到 BizTalk OracleEBS 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")</span><span class="sxs-lookup"><span data-stu-id="5dcea-114">![Add WCF&#45;OracleEBS adapter to BizTalk](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")</span></span>  
  
5.  <span data-ttu-id="5dcea-115">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="5dcea-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dcea-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dcea-116">See Also</span></span>  
 [<span data-ttu-id="5dcea-117">创建 Oracle E-business Suite 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="5dcea-117">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)