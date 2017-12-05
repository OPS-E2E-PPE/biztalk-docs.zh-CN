---
title: "验证使用 XSD 架构的消息实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eda0b76b3daff53290264169c5b2effe80a9e5c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="94c37-102">验证使用 XSD 架构的消息实例</span><span class="sxs-lookup"><span data-stu-id="94c37-102">Validating a Message Instance Using the Schema XSD</span></span>
<span data-ttu-id="94c37-103">本主题介绍如何使用 Microsoft?[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 内置到 RNPIP 程序集文件中的架构 XSD 文件之一来验证消息实例。</span><span class="sxs-lookup"><span data-stu-id="94c37-103">This topic describes how to validate a message instance using one of the schema XSD files that Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] has built into the RNPIPs assembly file.</span></span>  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="94c37-104">用架构 XSD 验证消息实例</span><span class="sxs-lookup"><span data-stu-id="94c37-104">To validate a message instance using the schema XSD</span></span>  
  
1.  <span data-ttu-id="94c37-105">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="94c37-105">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="94c37-106">上**文件**，指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="94c37-106">On the **File**, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="94c37-107">找到*\<驱动器\>*files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="94c37-107">Locate *\<drive\>*\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="94c37-108">在解决方案资源管理器，展开**RNPIPs**，右键单击你想要使用以验证消息实例，然后单击的 XSD 架构**属性**。</span><span class="sxs-lookup"><span data-stu-id="94c37-108">In Solution Explorer, expand **RNPIPs**, right-click the schema XSD that you want to use to validate a message instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="94c37-109">在属性页对话框中，单击**输入实例 Filename**，找到包含文件的文件夹、 选择消息实例 XML 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="94c37-109">In the Property Pages dialog box, click **Input Instance Filename**, locate the folder that contains the file, select the message instance XML file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="94c37-110">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="94c37-110">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="94c37-111">在解决方案资源管理器，右键单击你想要使用以验证消息实例，然后单击的 XSD 架构**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="94c37-111">In Solution Explorer, right-click the schema XSD that you want to use to validate a message instance, and then click **Validate Instance**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c37-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94c37-112">See Also</span></span>  
 <span data-ttu-id="94c37-113">[修改在 RNPIPs 现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span><span class="sxs-lookup"><span data-stu-id="94c37-113">[Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span></span>  
 [<span data-ttu-id="94c37-114">使用 PIP</span><span class="sxs-lookup"><span data-stu-id="94c37-114">Working with PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)