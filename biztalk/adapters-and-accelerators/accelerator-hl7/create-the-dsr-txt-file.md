---
title: "创建 DSR.txt 文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6947af7-c5ce-4ee6-9fe9-5c1094d0aee0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69520639040893aad7f46b29760343afa68073fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="create-the-dsrtxt-file"></a><span data-ttu-id="30c5e-102">创建 DSR.txt 文件</span><span class="sxs-lookup"><span data-stu-id="30c5e-102">Create the DSR.txt File</span></span>
<span data-ttu-id="30c5e-103">使用以下过程创建响应 DSR.txt 消息文件。</span><span class="sxs-lookup"><span data-stu-id="30c5e-103">Use the following procedure to create the response DSR.txt message file.</span></span> <span data-ttu-id="30c5e-104">你将更高版本使用此文件来验证教程的方案。</span><span class="sxs-lookup"><span data-stu-id="30c5e-104">You will use this file later to verify the tutorial scenario.</span></span>  
  
### <a name="to-create-the-dsrtxt-file"></a><span data-ttu-id="30c5e-105">若要创建 DSR.txt 文件</span><span class="sxs-lookup"><span data-stu-id="30c5e-105">To create the DSR.txt file</span></span>  
  
1.  <span data-ttu-id="30c5e-106">打开编辑器，如记事本，并将以下文本复制到编辑器：</span><span class="sxs-lookup"><span data-stu-id="30c5e-106">Open an editor, such as Notepad, and copy the following text into the editor:</span></span>  
  
    ```  
    MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
    MSA|AA|MSG00003  
    QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
    DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
    DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
    DSP|||ELECTROLYTES  
    DSP||| SODIUM 136 [135-148] MEQ/L STAT  
    DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
    DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
    DSP||| CO2 25 [20-30] MEQ/L STAT  
    DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
    ```  
  
2.  <span data-ttu-id="30c5e-107">将文件另存**DSR.txt**中\<*驱动器*:\>files\microsoft BizTalk\<版本\>HL7\SDK\Interrogative 快捷键教程文件夹，然后关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="30c5e-107">Save the file as **DSR.txt** in the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder, and then close the editor.</span></span>  
  
 <span data-ttu-id="30c5e-108">继续执行[步骤 1： 创建和部署常见标头和确认架构](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="30c5e-108">Proceed to [Step 1: Create and Deploy Common Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md).</span></span>