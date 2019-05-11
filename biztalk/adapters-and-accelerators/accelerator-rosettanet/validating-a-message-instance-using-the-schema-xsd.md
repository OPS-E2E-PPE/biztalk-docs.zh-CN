---
title: 验证消息实例使用的架构 XSD |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c8c234ecdb79b8aa2e15c99717396199514e29
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299949"
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="d4559-102">验证消息实例使用的架构 XSD</span><span class="sxs-lookup"><span data-stu-id="d4559-102">Validating a Message Instance Using the Schema XSD</span></span>
<span data-ttu-id="d4559-103">本主题介绍如何验证消息实例使用的架构 XSD 文件之一的 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]内置到 Rnpip 程序集文件。</span><span class="sxs-lookup"><span data-stu-id="d4559-103">This topic describes how to validate a message instance using one of the schema XSD files that Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] has built into the RNPIPs assembly file.</span></span>  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a><span data-ttu-id="d4559-104">若要验证消息实例使用的架构 XSD</span><span class="sxs-lookup"><span data-stu-id="d4559-104">To validate a message instance using the schema XSD</span></span>  
  
1.  <span data-ttu-id="d4559-105">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="d4559-105">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="d4559-106">上**文件**，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="d4559-106">On the **File**, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="d4559-107">找到*\<驱动器\>* \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\Schemas，单击**RNPIPs.btproj**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="d4559-107">Locate *\<drive\>* \Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas, click **RNPIPs.btproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="d4559-108">在解决方案资源管理器，展开**Rnpip**，右键单击架构 XSD，想要用于验证消息实例，然后依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="d4559-108">In Solution Explorer, expand **RNPIPs**, right-click the schema XSD that you want to use to validate a message instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="d4559-109">在属性页对话框中，单击**输入实例文件名**，找到包含该文件的文件夹、 选择消息实例 XML 文件，并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="d4559-109">In the Property Pages dialog box, click **Input Instance Filename**, locate the folder that contains the file, select the message instance XML file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="d4559-110">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d4559-110">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="d4559-111">在解决方案资源管理器中右键单击架构 XSD，想要用于验证消息实例，然后依次**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="d4559-111">In Solution Explorer, right-click the schema XSD that you want to use to validate a message instance, and then click **Validate Instance**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4559-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4559-112">See Also</span></span>  
 <span data-ttu-id="d4559-113">[修改 Rnpip 中的现有 PIP](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span><span class="sxs-lookup"><span data-stu-id="d4559-113">[Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md) </span></span>  
 [<span data-ttu-id="d4559-114">使用 PIP</span><span class="sxs-lookup"><span data-stu-id="d4559-114">Working with PIPs</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)