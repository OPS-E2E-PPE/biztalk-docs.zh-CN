---
title: 步骤 3： 编辑合作伙伴接口流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b5b6d2f6b0fcbf13ab521bc318eda54ece55f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003606"
---
# <a name="step-3-edit-the-partner-interface-process"></a><span data-ttu-id="35be2-102">步骤 3： 编辑合作伙伴接口流程</span><span class="sxs-lookup"><span data-stu-id="35be2-102">Step 3: Edit the Partner Interface Process</span></span>
<span data-ttu-id="35be2-103">在此步骤中，您可以编辑合作伙伴接口流程 (PIP) 配置设置，以便禁用安全传输，如果您没有在 Microsoft® Internet 信息服务 (IIS) 配置的安全套接字层 (SSL) 证书。</span><span class="sxs-lookup"><span data-stu-id="35be2-103">In this step, you edit the Partner Interface Process (PIP) configuration settings to disable secure transport if you do not have a Secure Sockets Layer (SSL) certificate configured in Microsoft® Internet Information Services (IIS).</span></span> <span data-ttu-id="35be2-104">由于环回方案不支持对传入消息和传出消息签名，为了继续完成教程，你必须更改默认设置。</span><span class="sxs-lookup"><span data-stu-id="35be2-104">Because the loopback scenario does not support signing for both incoming and outgoing messages, you must change the default settings to continue with the tutorial.</span></span> <span data-ttu-id="35be2-105">你将修改 STD_0C1_R01.02 PIP。</span><span class="sxs-lookup"><span data-stu-id="35be2-105">You modify the STD_0C1_R01.02 PIP.</span></span>  
  
### <a name="to-edit-the-std0c1r0102-pip"></a><span data-ttu-id="35be2-106">编辑 STD_0C1_R01.02 PIP</span><span class="sxs-lookup"><span data-stu-id="35be2-106">To edit the STD_0C1_R01.02 PIP</span></span>  
  
1. <span data-ttu-id="35be2-107">在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开**BizTalk\<版本\>Accelerator for RosettaNet**，单击**流程配置设置**，右键单击**STD_0C1_R01.02**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="35be2-107">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version\> Accelerator for RosettaNet**, click **Process Configuration Settings**, right-click **STD_0C1_R01.02**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="35be2-108">在 STD_0C1_R01.02Properties 对话框中，在**活动**选项卡上，设置**是否要求安全传输**选项设为`False`。</span><span class="sxs-lookup"><span data-stu-id="35be2-108">In the STD_0C1_R01.02Properties dialog box, on the **Activity** tab, set the **Is Secure Transport Required** option to `False`.</span></span> <span data-ttu-id="35be2-109">请只在 IIS Web 服务器上没有 SSL 证书的情况下执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="35be2-109">Perform this step only if you do not have a SSL certificate on your IIS Web server.</span></span>  
  
3. <span data-ttu-id="35be2-110">设置**要求不可否认**到`False`，将**是否要求授权**到`False`，将**和内容的不可否认**到`False`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35be2-110">Set the **Non-Repudiation Required** to `False`, set **Is Authorization Required** to `False`, set **Non-Repudiation of Origin and Content** to `False`, and then click **OK**.</span></span>  
  
    <span data-ttu-id="35be2-111">此操作禁用“不可否认性”，也禁止了签名消息证书的使用。</span><span class="sxs-lookup"><span data-stu-id="35be2-111">This disables non-repudiation and the use of certificates for signing messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35be2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="35be2-112">See Also</span></span>  
 <span data-ttu-id="35be2-113">[步骤 4： 创建贸易协议](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="35be2-113">[Step 4: Create a Trade Agreement](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md) </span></span>  
 [<span data-ttu-id="35be2-114">授权属性和不可否认性属性</span><span class="sxs-lookup"><span data-stu-id="35be2-114">Authorization and Non-Repudiation Properties</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)