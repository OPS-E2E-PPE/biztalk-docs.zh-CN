---
title: CIDX 支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, procedures
- CIDX, about CIDX
- CIDX, Elemica Exchange Server Provider (ESP)
- CIDX, PIPs
- CIDX
- Elemica Exchange Server Provider (ESP)
- procedures [CIDX]
- PIPs, CIDX
ms.assetid: 58b75ad3-f6b9-47c0-8dbf-506a3eaf010b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57500dc25e719d7ef693975b74850cbc04289dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997806"
---
# <a name="cidx-support"></a><span data-ttu-id="030d5-102">CIDX 支持</span><span class="sxs-lookup"><span data-stu-id="030d5-102">CIDX Support</span></span>
<span data-ttu-id="030d5-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]提供对 CIDX （化工行业数据交换） XML 消息交换的支持。</span><span class="sxs-lookup"><span data-stu-id="030d5-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides support for CIDX (Chemical Industry Data Exchange) XML message exchange.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="030d5-104"> 支持 CIDX Chem eStandards 2.0 和 3.0，两者都使用 RosettaNet 实现框架 (RNIF) 1.1 版。</span><span class="sxs-lookup"><span data-stu-id="030d5-104"> supports CIDX Chem eStandards versions 2.0 and 3.0, both of which use the RosettaNet Implementation Framework (RNIF) 1.1.</span></span>  
  
 <span data-ttu-id="030d5-105">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 异步简单公用流程（支持单操作和双操作消息）使用并路由 CIDX 服务内容。</span><span class="sxs-lookup"><span data-stu-id="030d5-105">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] asynchronous simple public processes (supporting single-action and double-action messages) consume and route CIDX service content.</span></span>  
  
 <span data-ttu-id="030d5-106">对于基于 CIDX PIP 的协议，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 在消息中验证以下内容：</span><span class="sxs-lookup"><span data-stu-id="030d5-106">For an agreement based on a CIDX PIP, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will validate the following in a message:</span></span>  
  
- <span data-ttu-id="030d5-107">仅 RNIF 1.1 版本</span><span class="sxs-lookup"><span data-stu-id="030d5-107">RNIF 1.1 version only</span></span>  
  
- <span data-ttu-id="030d5-108">非 0A1</span><span class="sxs-lookup"><span data-stu-id="030d5-108">No 0A1</span></span>  
  
- <span data-ttu-id="030d5-109">仅单操作</span><span class="sxs-lookup"><span data-stu-id="030d5-109">Only Single Action</span></span>  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="030d5-110"> 不会阻止您设置`Standard`流程配置为"CIDX"，在设置后的属性`0A1 agreement`使用该配置文件为"0A1"（这不支持为 CIDX） 为协议的属性。</span><span class="sxs-lookup"><span data-stu-id="030d5-110"> will not prevent you from setting the `Standard` property for a process configuration to "CIDX", after you have set the `0A1 agreement` property for an agreement that uses that profile to "0A1" (which is not supported for CIDX).</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="030d5-111"> 不执行会防止发生这跨字段验证。</span><span class="sxs-lookup"><span data-stu-id="030d5-111"> does not perform the cross-field validation that would prevent this.</span></span>  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a><span data-ttu-id="030d5-112">将 PIP 应用于 CIDX 实现</span><span class="sxs-lookup"><span data-stu-id="030d5-112">Applying a PIP to a CIDX Implementation</span></span>  
 <span data-ttu-id="030d5-113">若要将 PIP 应用于 CIDX 实现中，设置`Standard`到过程配置文件中的属性**CIDX**。</span><span class="sxs-lookup"><span data-stu-id="030d5-113">To apply a PIP to a CIDX implementation, set the `Standard` property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="030d5-114">完成后，你将能够为消息标准、 标准版本和负载绑定 id。 输入值</span><span class="sxs-lookup"><span data-stu-id="030d5-114">After you have finished, you will be able to enter values for the Message standard, Standard version, and Payload binding ID.</span></span> <span data-ttu-id="030d5-115">您可以在 CIDX Chem eStandards 规范中找到这些值。</span><span class="sxs-lookup"><span data-stu-id="030d5-115">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="030d5-116">连接到 Elemica 网络</span><span class="sxs-lookup"><span data-stu-id="030d5-116">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="030d5-117">可以使安装的 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]若要连接到 Elemica[!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)]提供商 (ESP)。</span><span class="sxs-lookup"><span data-stu-id="030d5-117">You can enable an installation of Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to connect to the Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] Provider (ESP).</span></span> <span data-ttu-id="030d5-118">您可以通过 Elemica 网络使用 CIDX 消息交换进行化工行业中的购买、销售和供应链管理。</span><span class="sxs-lookup"><span data-stu-id="030d5-118">You can use the Elemica network for chemical-industry buying, selling, and supply-chain management using CIDX message exchange.</span></span>  
  
 <span data-ttu-id="030d5-119">你自定义[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]以连接到 Elemica 使用 Elemica 连接包中的项目文件。</span><span class="sxs-lookup"><span data-stu-id="030d5-119">You customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="030d5-120">您可以下载连接包从[ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195)。</span><span class="sxs-lookup"><span data-stu-id="030d5-120">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="030d5-121">有关详细信息，请在 MSDN 上参阅"连接到 Elemica 网络使用 BizTalk Accelerator for RosettaNet 3.0"白皮书[ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539)。</span><span class="sxs-lookup"><span data-stu-id="030d5-121">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="030d5-122">“Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0”（使用 BizTalk Accelerator for RosettaNet 3.3 连接到 Elemica 网络）白皮书中的信息对 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 有效。</span><span class="sxs-lookup"><span data-stu-id="030d5-122">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="cidx-procedures"></a><span data-ttu-id="030d5-123">CIDX 过程</span><span class="sxs-lookup"><span data-stu-id="030d5-123">CIDX Procedures</span></span>  
 <span data-ttu-id="030d5-124">以下部分讲述如何设置 CIDX 消息交换：</span><span class="sxs-lookup"><span data-stu-id="030d5-124">The following sections described how to set up CIDX message exchange:</span></span>  
  
-   [<span data-ttu-id="030d5-125">设置 CIDX eStandards 消息交换</span><span class="sxs-lookup"><span data-stu-id="030d5-125">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [<span data-ttu-id="030d5-126">创建或编辑协议</span><span class="sxs-lookup"><span data-stu-id="030d5-126">Creating or Editing an Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [<span data-ttu-id="030d5-127">导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="030d5-127">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a><span data-ttu-id="030d5-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="030d5-128">See Also</span></span>  
 <span data-ttu-id="030d5-129">[BizTalk Accelerator for RosettaNet 向 BizTalk Server 的添加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="030d5-129">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="030d5-130">CIDX 消息传送标准</span><span class="sxs-lookup"><span data-stu-id="030d5-130">CIDX Messaging Standards</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)