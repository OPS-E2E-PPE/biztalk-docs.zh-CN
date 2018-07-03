---
title: 准备使用 Tutorial2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, pre-requisites
ms.assetid: 88e6c0b5-5f7d-4fee-a4de-7922cfba917f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d790a53576c4f153265531fca974089eb5292a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978654"
---
# <a name="preparing-to-use-the-tutorial"></a><span data-ttu-id="6a2c7-102">为使用教程做准备</span><span class="sxs-lookup"><span data-stu-id="6a2c7-102">Preparing to Use the Tutorial</span></span>
<span data-ttu-id="6a2c7-103">使用本教程之前，需要创建一个 ADT^A03.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="6a2c7-103">Before you use the tutorial, you need to create an ADT^A03.txt file.</span></span>  
  
### <a name="to-create-the-adta03txt-file"></a><span data-ttu-id="6a2c7-104">若要创建 ADT^A03.txt 文件</span><span class="sxs-lookup"><span data-stu-id="6a2c7-104">To create the ADT^A03.txt file</span></span>  
  
1. <span data-ttu-id="6a2c7-105">打开编辑器 （如记事本），并将以下文本复制到编辑器：</span><span class="sxs-lookup"><span data-stu-id="6a2c7-105">Open an editor such as Notepad and copy the following text into the editor:</span></span>  
  
   ```  
   MSH|^~\&|Tutorial_ADTSystem|MCM|BTAHL7InterfaceEngine||199601121005||ADT^A03|000001|P|2.3.1  
   EVN|A03|199601121005||01||199601121000  
   PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||  
       123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
   PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|  
      NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P  
      ^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString  
      ^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString  
      ^Test^Test^NormalString^Test|N  
   PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="6a2c7-106">应该有五个行中的.txt 文件，分别与"MSH"、"EVN"、"PID"、"PD1"和"PV1"正在启动。</span><span class="sxs-lookup"><span data-stu-id="6a2c7-106">There should be five lines in the .txt file, one each starting with "MSH", "EVN", "PID", "PD1", and "PV1".</span></span> <span data-ttu-id="6a2c7-107">你将需要删除"PID"行和"PD1"行中的空间。</span><span class="sxs-lookup"><span data-stu-id="6a2c7-107">You will need to remove the spaces within the "PID" line and the "PD1" line.</span></span> <span data-ttu-id="6a2c7-108">如有必要，请关闭记事本中的自动换行。</span><span class="sxs-lookup"><span data-stu-id="6a2c7-108">If necessary, turn off word wrap in Notepad.</span></span>  
  
2. <span data-ttu-id="6a2c7-109">将该文件作为**ADT^A03.txt**中\<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator forHL7\SDK\End 端到端教程文件夹，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="6a2c7-109">Save the file as **ADT^A03.txt** in the \<*drive*\>:\Program Files\\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial folder, and then close Notepad.</span></span>  
  
   <span data-ttu-id="6a2c7-110">请继续执行[步骤 1： 创建和部署标头及确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="6a2c7-110">Proceed to [Step 1: Create and Deploy Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md).</span></span>