---
title: 将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
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
ms.openlocfilehash: b11a6959ecffb7447c577153104977bd90815105
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375815"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="bf661-102">将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="bf661-102">Add the Oracle E-Business Suite adapter to BizTalk Server Administration console</span></span>
<span data-ttu-id="bf661-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可作为 WCF 自定义端口或 WCF OracleEBS 端口在 BizTalk Server 中使用。</span><span class="sxs-lookup"><span data-stu-id="bf661-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] can be used in BizTalk Server either as a WCF-Custom port or a WCF-OracleEBS port.</span></span> <span data-ttu-id="bf661-104">如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。</span><span class="sxs-lookup"><span data-stu-id="bf661-104">If you want to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="bf661-105">但是，如果你想要使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过 WCF OracleEBS 端口，必须首先添加到 WCF OracleEBS 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf661-105">However, if you want to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] through a WCF-OracleEBS port, you must first add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="bf661-106">本主题说明了如何将 WCF OracleEBS 适配器添加到添加[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf661-106">This topic provides instructions on how to add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf661-107">如果你想要配置的 WCF 自定义端口[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，则不需要执行此过程。</span><span class="sxs-lookup"><span data-stu-id="bf661-107">If you want to configure a WCF-Custom port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you need not perform this procedure.</span></span>  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="bf661-108">若要添加 Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="bf661-108">To add the Oracle E-Business Suite Adapter</span></span>  
  
1. <span data-ttu-id="bf661-109">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="bf661-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="bf661-110">在控制台树中，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="bf661-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="bf661-111">右键单击**适配器**，依次指向**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="bf661-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="bf661-112">![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="bf661-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="bf661-113">在中**适配器属性**对话框框中，指定名称的适配器，从**适配器**列表中，选择**Wcf-oracleebs**。</span><span class="sxs-lookup"><span data-stu-id="bf661-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-OracleEBS**.</span></span>  
  
    <span data-ttu-id="bf661-114">![添加 WCF&#45;OracleEBS 适配器添加到 BizTalk](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")</span><span class="sxs-lookup"><span data-stu-id="bf661-114">![Add WCF&#45;OracleEBS adapter to BizTalk](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")</span></span>  
  
5. <span data-ttu-id="bf661-115">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="bf661-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf661-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf661-116">See Also</span></span>  
 [<span data-ttu-id="bf661-117">若要创建 Oracle E-business Suite 的应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="bf661-117">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)