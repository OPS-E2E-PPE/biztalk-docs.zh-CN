---
title: 创建 QRY^Q01.txt 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ac96587-264f-4743-a90b-4763d330e320
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0415fda29737c68811f9a6ad51a58e05e26436cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977982"
---
# <a name="create-the-qryq01txt-file"></a><span data-ttu-id="38b60-102">创建 QRY^Q01.txt 文件</span><span class="sxs-lookup"><span data-stu-id="38b60-102">Create the QRY^Q01.txt File</span></span>
<span data-ttu-id="38b60-103">使用以下过程创建患者查询 QRY^Q01.txt 消息文件。</span><span class="sxs-lookup"><span data-stu-id="38b60-103">Use the following procedure to create the patient query QRY^Q01.txt message file.</span></span> <span data-ttu-id="38b60-104">您将更高版本使用此文件以验证教程的方案。</span><span class="sxs-lookup"><span data-stu-id="38b60-104">You will use this file later to verify the tutorial scenario.</span></span>  
  
### <a name="to-create-the-qryq01txt-file"></a><span data-ttu-id="38b60-105">若要创建 QRY^Q01.txt 文件</span><span class="sxs-lookup"><span data-stu-id="38b60-105">To create the QRY^Q01.txt file</span></span>  
  
1. <span data-ttu-id="38b60-106">打开编辑器 （如记事本），并将以下文本复制到编辑器：</span><span class="sxs-lookup"><span data-stu-id="38b60-106">Open an editor, such as Notepad, and copy the following text into the editor:</span></span>  
  
   ```  
   MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
   QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
   ```  
  
2. <span data-ttu-id="38b60-107">将该文件作为**QRY^Q01.txt**中\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\ 的快捷键询问教程文件夹，然后再关闭编辑器。</span><span class="sxs-lookup"><span data-stu-id="38b60-107">Save the file as **QRY^Q01.txt** in the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder, and then close the editor.</span></span>  
  
   <span data-ttu-id="38b60-108">请继续执行[创建 DSR.txt 文件](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md)。</span><span class="sxs-lookup"><span data-stu-id="38b60-108">Proceed to [Create the DSR.txt File](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md).</span></span>